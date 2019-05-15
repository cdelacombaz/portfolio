# Create responsive portfolio website

This website has been created following a tutorial from Traversy Media. I wanted to have a portfolio to show to potential employeers and also refresh and enhance my SASS skills. Here are some notes about what I learned working on this project:


#### The browser can’t read scss. We need to set up a compiler to compile it to CSS

-   In the project folder run `npm init` to install package.json file, which is like a manifest

-   After that install sass with `npm i node-sass``

-   Setting up the script:

```
"scripts": {
        "sass": "node-sass -w scss/ -o dist/css/ --recursive"
    },
```

-w scss/ => watch the scss folder
-o dist/css/ => output compiled sass in css folder
-- recursive => needed to avoid issues with partials and auto-reload

-   `npm run sass` to run the script. Now if we do changes in the main.scss file, it should compile it to our main.css file

#### fontawesome.com icons

Adding fontawesome link in index.html will make a lot of icons like twitter, facebook etc. available. They can be used by adding HTML tags like `<i class="fab fa-twitter"></i>`. Classes need to be checked on fontawesome.com

#### SASS and styling

-   Responsive design: By creating mixins for different display sizes, we can add styling to each of them. The displayed screen size in pixel will then get the respective style and make it look good on any configured media. For example, the grid in my about-me section is reduce to 1 fraction instead of 3 when seen on mobiles.

-   Nested classes: `h1 { .heading () }` will style any h1-nested tag which has .heading as class. `h1 { &.heading {} }` will style h1 with .heading as class.

-   Mixin: Are like functions. They can be declared with `@mixin mixinName { statement }` and be used with `@include mixinName`.

-   Mixin are not functions: Mixins can not return anything. We need to write a function to manage the text color depending on the background color being light or dark. `@function myFunctionName($myParamName) { statement }` To use a function we can call it without the include prefix. `myFunctionName($myArgName)`

-   For loop in SASS: `@for $x from 1 through 4 {.nav-item:nth-child(#{$x}) { styling }}` \$x is a variable we set and to use it in the loop, we need to wrap it in a number sign `#{$var}`. I used this to slide in the nav items with a delay.

-   Create a sticky footer: We can use following code to set the minimum height of the content to 100 viewheight - the height of the footer `min-height: calc(100vh - 60px);`

-   rem: A rem is a multiplyer of the HTML tag font-size (default 1rem = 16px)

-   em: An em is a multiplyer of the parent tag font-size

-   lighten() and darken(): takes 2 arguments, color and a number. This will lighten or darken the color the color: `lighten($primary-color, 2);`. Lighten is changing the color, but if we want some opacity to see a background color, we have to wrap it in a rgba function `background: rgba(lighten($primary-color, 2), 0.5);`.

-   CSS transitions: something that takes time to do. For example sliding something in, fading something out, changing color etc.
    transition takes 3 arguments: (what do we move) (how many seconds will it take) (motion / how do we move)

-   CSS translate3d:

-   Sudo element: before or after elements can be used instead of additional html elements. Here instead of creating a div for the grey overlay, we can use `:after { content: '', .... }`.

-   `&copy;` is the HTML entity for the copyright symbol

-   Thanks to emmet we can type `Lorem30` or any other number and then tab. This will create a sample text with 30 words.
