# Create responsive portfolio website

Tutorial by Traverse Media: https://www.youtube.com/watch?v=gYzHS-n2gqU&list=PLillGF-RfqbYoGoCjKoMOkVznV6aSXKzU&index=1

## Step by step guide

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
