# Helper Methods

## Tasks

## Write some tests

Read Sections 1, 2, 4, 5, 6, and 7 of the [Rails Guide on Testing](https://guides.rubyonrails.org/testing.html). These are the kinds of tests that we write most frequently.

Then, take a stab at writing some System tests to lock down the current functionality of the application. After you've spent 20-30 minutes on it, you're allowed to look at the example specs in `test/system/example_movies_test.rb`.

### Clean-ups that we already know how to do

 - Anywhere you see the old `Hash` syntax (`:symbol` keys with hash rockets `=>`): switch to [the new `Hash` syntax](https://chapters.firstdraft.com/chapters/787#new-hash-syntax).
 - Anywhere you see [optional curly braces around `Hash` arguments](https://chapters.firstdraft.com/chapters/787#curly-braces-around-hash-arguments): remove them.
 - Where possible, drop `render` statements.
 - When providing keys to `params`, use `Symbol`s. (Unlike with most hashes, you can use `String`s and `Symbol`s interchangeably as keys to `params`.)

### Refactor routes

 - Re-write routes using more succinct forms of `get`, `post`, `patch`, `delete`, and, ultimately, `resources`.

### First new helper methods

 - Replace all references to URLs outside of `config/routes.rb` with route helper methods.
 - Replace all `<a>` elements in view templates with `link_to` methods.

### Forms in general

 - Replace all `<form>` elements in view templates with `form_with` methods.
 - Replace all `<input>` elements with `text_field_tag`, `number_field_tag`, `text_area_tag`, etc.
 
### Forms specifically for model objects

 - Change the names of inputs so that values in the `params` hash are nested within an inner hash.
 - Assign all of the values at once using ActiveRecord's mass assignment ability via `new` or `update`.
 - Whitelist which attributes you want to allow to be mass assigned from `params` with `params.require(:movie).permit(:title, :description)`.
 - Switch from `form_with(url:)` to `form_with(model:)`
 - Switch from `text_field_tag`, etc; to `form.text_field`, etc.
 - Move form to partial and re-use wherever possible.
