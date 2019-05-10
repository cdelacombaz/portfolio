# Create responsive portfolio website

Tutorial by Traverse Media: https://www.youtube.com/watch?v=gYzHS-n2gqU&list=PLillGF-RfqbYoGoCjKoMOkVznV6aSXKzU&index=1

## Step by step guide to setup SASS compiler

-   Create dist folder (this is where our HTML, compiled CSS, JavaScript, images etc. goes) - create index.html

-   Create css folder - create main.scss (this is the main file. All other scss files will be partials that are imported into this main file)

### The browser can’t read scss. We need to set up a compiler to compile it to CSS

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

## Things I learned

### fontawesome.com icons

Adding fontawesome link in index.html will make a lot of icons like twitter, facebook etc. available. They can be used by adding HTML tags like `<i class="fab fa-twitter"></i>`. Classes need to be checked on fontawesome.com

### SASS and styling

-   Nested classes: `h1 { .heading () }` will style any h1-nested tag which has .heading as class. `h1 { &.heading {} }` will style h1 with .heading as class.

-   Mixin: Are like functions. They can be declared with `@mixin mixinName { statement }` and be used with `@include mixinName`.

-   For loop in SASS: `@for $x from 1 through 4 {.nav-item:nth-child(#{$x}) { styling }}` \$x is a variable we set and to use it in the loop, we need to wrap it in a number sign `#{$var}`. I used this to slide in the nav items with a delay.

-   rem: A rem is a multiplyer of the HTML tag font-size (default 1rem = 16px)

-   em: An em is a multiplyer of the parent tag font-size

-   lighten() and darken(): takes 2 arguments, color and a number. This will lighten or darken the color the color: `lighten($primary-color, 2);`. Lighten is changing the color, but if we want some opacity to see a background color, we have to wrap it in a rgba function `background: rgba(lighten($primary-color, 2), 0.5);`.

-   CSS transitions: something that takes time to do. For example sliding something in, fading something out, changing color etc.
    transition takes 3 arguments: (what do we move) (how many seconds will it take) (motion / how do we move)

-   CSS translate3d:

-   Sudo element: before or after elements can be used instead of additional html elements. Here instead of creating a div for the grey overlay, we can use `:after { content: '', .... }`.
