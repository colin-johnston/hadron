# [Hadron](https://github.com/electronspin/hadron)

**Hadron is a WordPress starter theme built upon Sage, using Foundation for Sites 6.2.**

[**Sage**](https://roots.io/sage/) is a WordPress starter theme based on HTML5 Boilerplate, gulp, Bower (and Bootstrap Sass, originally) that will help you make better themes. Sage is produced and maintained by Ben Word and the team at [Roots](https://roots.io).

[**Foundation for Sites**](http://foundation.zurb.com/sites.html) is a front-end framework for rapidly building content-focused websites. It includes a wide range of modular and flexible components that are easily styled. Foundation for Sites is produced and maintained by the team at [ZURB](http://www.zurb.com/)

## Requirements

| Prerequisite    | How to check | How to install
| --------------- | ------------ | ------------- |
| PHP >= 5.4.x    | `php -v`     | [php.net](http://php.net/manual/en/install.php) |
| Node.js 0.12.x  | `node -v`    | [nodejs.org](http://nodejs.org/) |
| gulp >= 3.8.10  | `gulp -v`    | `npm install -g gulp` |
| Bower >= 1.3.12 | `bower -v`   | `npm install -g bower` |

For more installation notes, refer to the [Install gulp and Bower](#install-gulp-and-bower) section in this document.

## Sage Features

* [gulp](http://gulpjs.com/) build script that compiles both Sass and Less, checks for JavaScript errors, optimizes images, and concatenates and minifies files
* [BrowserSync](http://www.browsersync.io/) for keeping multiple browsers and devices synchronized while testing, along with injecting updated CSS and JS into your browser while you're developing
* [Bower](http://bower.io/) for front-end package management
* [asset-builder](https://github.com/austinpray/asset-builder) for the JSON file based asset pipeline
* [Foundation for Sites](http://foundation.zurb.com/sites.html) 6.2 (now with [Babel](https://babeljs.io/) integration)
* Sage [Theme wrapper](https://roots.io/sage/docs/theme-wrapper/)
* ARIA roles and microformats
* Posts use the [hNews](http://microformats.org/wiki/hnews) microformat
* [Multilingual ready](https://roots.io/wpml/) and over 30 available [community translations](https://github.com/roots/sage-translations)

Install Roots' [Soil](https://github.com/roots/soil) plugin to enable additional features:

* Cleaner output of `wp_head` and enqueued assets
* Cleaner HTML output of navigation menus
* Root relative URLs
* Nice search (`/search/query/`)
* Google CDN jQuery snippet from [HTML5 Boilerplate](http://html5boilerplate.com/)
* Google Analytics snippet from [HTML5 Boilerplate](http://html5boilerplate.com/)


## Theme installation

How to get the files in this repo into your local development environment:

### via Command-line

To pull the latest version of Hadron into your working theme directory:

*Note: it is recommended to complete the [theme setup](#theme-setup) and initial steps of [theme development](#theme-development) before activating Hadron in your WordPress installation.*



```sh
cd your-project/wp-content/themes
git clone https://github.com/electronspin/hadron.git your-theme-name && cd your-theme-name

```

Then activate the theme via [wp-cli](http://wp-cli.org/commands/theme/activate/).

```sh
wp theme activate your-theme-name
```

### via WordPress Admin Panel

1. [Download the latest release](https://github.com/electronspin/hadron/releases/latest) of Hadron.
2. In your WordPress admin panel, navigate to Appearance->Themes
3. Click Add New
4. Click Upload Theme
5. Upload the zip file that you downloaded.

## Theme setup

Edit `lib/setup.php` to enable or disable theme features, setup navigation menus, post thumbnail sizes, post formats, and sidebars.

## Theme development

Sage uses [gulp](http://gulpjs.com/) as its build system and [Bower](http://bower.io/) to manage front-end packages.

### Install gulp and Bower

Building the theme requires [node.js](http://nodejs.org/download/). We recommend you update to the latest version of npm: `npm install -g npm@latest`.

From the command line:

1. Install [gulp](http://gulpjs.com) and [Bower](http://bower.io/) globally with `npm install -g gulp bower`

### Install dependencies

Also from the command line:

Navigate to the theme directory, then run

1. `npm install`

1. `bower install`

You now have all the necessary dependencies to run the build process.

### Using gulp

Once you've installed NPM and Bower dependencies---but before you activate the theme---you need to compile the assets:

From your theme directory, run `gulp` 

#### Available gulp commands

* `gulp` — Compile and optimize the files in your assets directory
* `gulp watch` — Compile assets when file changes are made
* `gulp --production` — Compile assets for production (no source maps).

For more info about gulp, and to learn how to customize your builds, go to [gulp.js](http://gulpjs.com/)

### Using BrowserSync

To use BrowserSync during `gulp watch` you need to update `devUrl` at the bottom of `assets/manifest.json` to reflect your local development hostname.

For example, if your local development URL is `http://project-name.dev` you would update the file to read:
```json
...
  "config": {
    "devUrl": "http://project-name.dev"
  }
...
```
If your local development URL looks like `http://localhost:8888/project-name/` you would update the file to read:
```json
...
  "config": {
    "devUrl": "http://localhost:8888/project-name/"
  }
...
```

For more info about BrowserSync, go to [browsersync.io](https://www.browsersync.io/)
### Local development using Wocker

I really like using Wocker for quick POCs and experiments.

Wocker is a Docker-based rapid development environment of WordPress that runs inside a Vagrant box.

See the [Getting Started](http://wckr.github.io/#h2-1) guide to get up and running.

## Documentation

This README (which is a variation of the original [Sage README](SAGE_README.md)) is the extent of documentation needed to get up and runnning. 

**Sage** documentation is available at [https://roots.io/sage/docs/](https://roots.io/sage/docs/).

**Foundation for Sites** documentation is available at [http://foundation.zurb.com/sites/docs/](http://foundation.zurb.com/sites/docs/)

## Contributing

Contributions to Hadron are welcome from everyone. If you'd like to contribute to Sage or Foundation check out their respective repos.

## Social

This is my first project of this kind, and I'd appreciate any encouragement, suggestions, bug fixes, or general OSS guidance. Reach me [@colinjohnston](https://twitter.com/colinjohnston) or colin [at] electronspin [dot] com


Thanks to Ben Word ([@retlehs](https://twitter.com/retlehs)) and the team at Roots for creating Sage; I'm learning some good habits reading through your code and working with your tools. And thanks to the folks [@ZURB](https://twitter.com/ZURB) for creating Foundation---although the upgrade path from one major version to the next can be pretty hectic, it really is (in my opinion) the best heavy-duty front-end framework out there.


