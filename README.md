# Bootstrap custom.json Fork (v.3.3.1)

A quick-and-dirty hack to allow a [Grunt](http://gruntjs.com) build of [Bootstrap](http://getbootstrap.com) using the `custom.json` file created by [Bootstrap Customizer](http://getbootstrap.com/customize/)

## Quick use

Requires node.js. To install run: 

```
npm install
```

Go to the [Customizer](http://getbootstrap.com/customize/) and create a `custom.json` file. Save the file in the root directory and run:

```
grunt config
```

## Changes to original.

Only two files are changed: `package.json` and `Gruntfile.js` in the root directory. `package.json` has only one addition: `grunt-replace` added in devDependencies. All changes in the Gruntfile are marked with the comment "HACK by @sprawld"

This is a fork of Bootstrap v3.3.1. I'll try and keep it up to date, but do check the [original repo](https://github.com/twbs/bootstrap).

### Motivation

I found it annoying that I couldn't download the latest version of Bootstrap, and build it with Grunt, keeping all my custom settings without either:

 a) copying in a customised variables.less, bootstrap.less and changing the list of javascript files in the Gruntfile. or:

 b) uploading my previous `config.json` to the customizer web front-end (I'm a programmer, I can't use a mouse)
 
So, I hacked the `Gruntfile.js`, using [grunt-replace](https://github.com/outaTiME/grunt-replace) to create a two modified files in the less/ directory: `variables-custom.less` and `bootstrap-custom.less`.
It then builds the custom CSS and Javascript, and copies the Glyphicon fonts (the same as running `grunt dist`)
