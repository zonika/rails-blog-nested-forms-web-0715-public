---
tags: rails, nested resources, strong params, complex nested forms
language: ruby
resources: 3
---

# Rails Blog Nested Resources and Forms

We're going to build off our previous iteration of our Blog App, where we created new models for Users and Tags (and applicable associations) and wrote validations. We want to clean up our tagging feature and add a feature that allows a user to comment on a post.

Our ability to add tags to a new post is super useful, but what if when we're making a new post, as want to add a new tag that isn't in the list? Let's build that out.

## Tags

1. We need to change the permitted params in our post controller to accept another attribute: `:tags_attributes`, which permit the tag attributes that we need to create a new tag.
2. `accepts_nested_attributes_for` on Post model, which will permit tags to be nested in our new post form.
3. Now we can build a nested form on our Post form. Check out the documentation on [Nested Forms](http://guides.rubyonrails.org/form_helpers.html#nested-forms) for help.
4. We should be able to select previously create tags, as well as create a new tag.

## Comments

We're also going to build out a feature where someone can comment on a post. We need to:

1. Create a migration, model, and controller (let's generate these like we did before, using rails generate model and rails generate controller).
2. Comments only have value when they're associated with a post, so we're going to nest them in our routes under post.
3. Comments are made when we're looking at an individual post. The action will be handled on our Comments controller, but they will be posted on the Post show page.
4. We need to have the suggestion params permitted on our Post controller