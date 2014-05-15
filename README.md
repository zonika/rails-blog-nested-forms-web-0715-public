---
tags: rails, nested resources, strong params, complex nested forms
language: ruby
resources: 3
---

# Rails Blog Nested Resources and Forms

We're going to build off our previous iteration of our Blog App, where we created new models for Users and Tags (and applicable associations) and wrote validations.

When we built out that checkbox collection, you might have noticed that while useful, it probably wasn't the best way to go about adding tags to a post. Ideally, we want a user to be able to add tags to a post as they're writing a post. Let's do just that.

## Tags

1. While we're at it, let's build out a tag show page that lists all posts associated with a tag.
2. 

## Comments

We're also going to build out a feature where someone can comment on a post. We need to:

1. Create a migration, model, and controller (let's generate these like we did before).
2. Comments only have value when they're associated with a post, so we're going to nest them in our routes under post.
3. Comments are made when we're looking at an individual post. The action will be handled on our Comments controller, but they will be posted on the Post show page.
4. We need to have the suggestion params permitted on our Post controller