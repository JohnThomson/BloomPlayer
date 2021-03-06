# BloomPlayer
Navigate Bloom books while basking in sound and motion

BloomPlayer.js is consumed by the Bloom Desktop project. When dropped into a Bloom Book html file, it provides a basic "player" that work in browsers and phone apps. The BloomPlayer handles:

* turning pages
* adjusting to device screens

For Bloom books with multimedia content, BloomPlayer handles
* playing narration
* hilighting sentences as you listen to narration (TODO)
* Ken Burns-style animation
* background music

## Dependencies
Node version >= 5.0 and NPM >= 3**.

## Building
    npm install
    webpack

For a continuous build:

    webpack -w

For a production build:

    npm run build:prod

## Testing with a book while hacking on the code

You'll need to get a Bloom book, then add a link with a path to the bloomPlayer.js in it. There are a couple ways to do that:

If you will be using a file system URL, you can do:

```<script src="path-to-bloomPlayer/output/bloomPlayer.js"></script>```

But that doesn't work well if you're testing via a server. If instead you set up a hardlink so that it looks like the file is there:

    mklink /H bloomPlayer.js the-path-to-the-actual-bloomPlayer.js # windows example

 then you can just put

```<script src="bloomPlayer.js"></script>```

and it will always use your latest, whether you're running from a server or the file system.
