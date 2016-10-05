# Turbolinks Challenge

| **Objectives** |
| :---- |
| Explore javascript in rails |
| Make use of `remote: true` for unobtrusive improvements to your page |
| Discover Turbolinks & Turbolinks Events |
| Organize javascript to only execute on specific pages |

**Terms:**
- Javascript Events
- Event Listener / Event Binding
- Turbolinks

##Instructions

Just clone, bundle, `rake db:setup` and then run `rails server`.

#### Challenge 1 - Whack A Mole   ----------------- SKIP FOR NOW

Use `remote: true` to make the delete request.  Be sure to tie your javascript into the appropriate [jquery_ujs](https://github.com/rails/jquery-ujs/wiki/ajax) ajax events.

Visit [localhost:3000/whack_a_mole](http://localhost:3000/whack_a_mole) to get started.  You should be able to gray-out the image and disable the button after each mole is deleted.  Make sure the page isn't refreshing!


#### Challenge 2 - Color Changer

**For this challenge you should work exclusively in your javascript directory: `app/assets/javascripts/`.**


When you click on a color page, your background color should change to match the name of the color in your url path. Can you fix the current javascript? (Your homepage should _not_ be teal!)

- Does it work on refresh?
- Does it work when you click through to the page?
- Is your solution DRY?

<details>
<summary>**Hint**: How would you grab the _path_ for the current page from the URL bar? (Click Here)</summary>
<br>
```js
window.location.pathname
// or, just
location.pathname
```
</details>

<details>
<summary>**Hint**: How would you grab the _color_ for the current page from the path? (Click Here)</summary>
<br>
```js
location.pathname.split("/")[1]; // warning: returns "" if path is "/"!
```
</details>

#### Challenge 3 - Page View Counter

**For this challenge you should work exclusively in your javascript directory: `app/assets/javascripts/`.**

The counter should increase for every individual page view.  Can you fix the current javascript?

- Do all the numbers reset when you refresh? (good!)
- Do specific numbers increment on each pageview?
- Is your solution DRY?

#### Challenge 4 - Be More Specific
**Page Specific CSS**: Can you think of a way to get the desired "Color Changer" behavior, without using _any_ javascript? (You may change only `application.html` and page specific `css` files).

<details>
<summary>**Hint**: Namespace your CSS to only apply to certain pages (Click Here)</summary>
<br/>
Identify the current page using an html `class` attribute, an `erb` tag, and the name of the current controller:
```html
<!-- app/views/layouts/application.html.erb -->
<body class="<%= page_specific_identifier %>">
    <!-- ... -->
</body>
```
<br/>
Reference the page specific `class` (i.e. the controller name and method name) in your stylesheet:
```css
/* app/assets/stylesheets/name_of_controller.css */
body.controller_name.method_name p {
    /*  
     *  the styles inside here will only apply to p tags
     *    that are nested inside body tags
     *      that have the "page_specific_identifier" id
     */
}
```

</details>

**Page Specific JS**: Create a pop-up that says "Welcome to teh best page" whenever a user lands on `/goldenrod` for the first time (but _not_ when they click through).

#### Bonus
**Track Your Visitors**: Rememeber that a visitor has already been "welcome[d] to teh best page", and do not welcome them again (they are already welcome).

<details>
<summary>**Hint**: Hmm, how would you remember that on the front-end? (Click Here)</summary>
<br>
Use a [cookie](http://letmegooglethat.com/?q=set+cookie+javascript+-w3schools), or [localstorage](https://developer.mozilla.org/en-US/docs/Web/API/Storage/LocalStorage)!
</details>

## Resources
- [Turbolinks Events](https://github.com/turbolinks/turbolinks-classic#events)
- [Conditional Execution of Page Specific Javascript](https://railsapps.github.io/rails-javascript-include-external.html#conditional)

<img width="400" src="https://media.giphy.com/media/l2Je2UKgDMm2HMqha/giphy.gif">
