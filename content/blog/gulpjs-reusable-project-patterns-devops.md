---
title: Gulp.JS - Reusable Project Patterns
subtitle: A powerful toolkit to help web developers save time
excerpt: >-
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
  incididunt ut labore et dolore magna aliqua.
date: '2017-06-29'
thumb_image: images/1484835114gulp-cover.png
thumb_image_alt: White concrete building wall
image: images/1484835114gulp-cover.png
image_alt: White concrete building wall
seo:
  title: Gulp.JS - Reusable Project Patterns
  description: >-
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Gulp.JS - Reusable Project Patterns
      keyName: property
    - name: 'og:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
      keyName: property
    - name: 'og:image'
      value: images/1484835114gulp-cover.png
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Gulp.JS - Reusable Project Patterns
    - name: 'twitter:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
    - name: 'twitter:image'
      value: images/1484835114gulp-cover.png
      relativeUrl: true
layout: post
---

[Gulp](http://gulpjs.com/) is a powerful toolkit to help web developers save time by performing automated tasks on a per-project basis. It's often used to do front end tasks like:

- Spinning up a NodeJS server or automate deployment of files
- With BrowserSync you can refresh a localhost page when saving changes to a file
- Using preprocessors like Sass or LESS
- Optimizing and concatenating assets like CSS, JavaScript
- Expand HTML by including template engines like [Handlebars](http://handlebarsjs.com/)

This is by no means all it does, but using Gulp to help with some basic tasks can really help speed up your daily development work-flow. Let's take a look at a minimal `gulpfile.js` file and setup some basic tasks that you would typically create when starting a new project.

### Getting Started with Gulp.js

**Step 1 - Install Node.js**

The first thing to getting Gulp.js setup is to make sure you have [Node.js](https://nodejs.org/en/download/) installed with NPM (Node Package Manager). Click the link and follow the install instructions. Node is a JavaScript runtime that manages dependencies and does some heavy lifting for us while using Gulp.JS and other similar tools.

**Step 2 - Verify Node Install**

With Node installed now, you can type:

```
node -v
```

into your terminal / console and you should see the latest version of Node.js returned:

```
v6.3.1
```

Once you've installed Node.js, you can **make sure you've got the very most recent version of npm using npm itself:**

```
sudo npm install npm -g
```

On Windows, you can drop the “sudo” but you should _run it as administrator_. Running this update will give you the most recent stable version of npm, also supported by npm Inc. The `-g` on the end tells npm to install npm "globally" allowing you to use npm from a terminal / console anywhere on your machine (not just inside of a specific project folder).

**Step 3 - Install Gulp.js**

With npm ready to go, simply type:

```
npm install gulp-cli -g
npm install gulp -D
```

Now you have Gulp on your machine, installed globally, ready to go!

### Adding Gulp to a new (or existing) Project

Now that Gulp.js is installed, you're ready to start automating some work-flow! Let's setup a package.json file for Node and a gulpfile.js for Gulp - both inside the root folder of your project.

**Why do I need a package.json file?**

NPM requires a package.json file to manage some basic info about your project and to also use as a place to save any dependancies you might need for your project (Twitter Bootstrap, or maybe jQuery, for example). By adding and saving dependancies, you can quickly and easily load project required items, or keep them up to date with the latest changes by a simple terminal command. You can [learn more about package.json here](https://docs.npmjs.com/files/package.json).

**Create package.json**

Thankfully, Node helps you in the creation of this file. Navigate to the project folder inside your terminal / command prompt and type:

```
npm init
```

Node will ask you a bunch of questions, and then write a package.json for you. It attempts to make reasonable guesses about what you want things to be set to, and then writes a package.json file with the options you've selected.

If you already have a package.json file, it'll read that first, and default to the options in there. It is strictly additive, so it does not delete options from your package.json without a really good reason to do so.

Now with your package.json file generated you can start making that Gulp.js file!

Their are plenty of GulpJS articles online on how to make and formulate your gulp file. They do a great job and helped even me learn how to make and customize Gulp for my projects.

After playing around for a year or so I've come up with my boilerplate that I use for almost every front-end project.

### Virtually(Creative) Default Gulp.js Boilerplate

I've pasted an example of one I personally use for a blank, full-scale single-page application. While it makes no assumptions about what you're going to use, I do assume a few things with this setup:

- /app/ folder is your development folder and holds all the files of the SPA
    - /app/ folder has a BrowserSync function to use during development and needs to be run to view.

- /demo/ is created from /app/ and lets you test the build instructions
    - /demo/ folder has a BrowserSync function to use during development and is auto-started after build
    - Images are cached upon the first build, will only update if changes are made then after for faster builds
    - Uses the awesome Rollbar Error reporting service to push errors to a Rollbar project, can be disabled.
    - dependencies needed from Node are moved into /vendor/ folder

- /dist/ folder is your PRODUCTION folder and is the production build of /app/
    - /dist/ folder has a BrowserSync function to use during testing, it needs to be run to view.
    - All JS/CSS files are concatenated into a single CSS and JS file called "main-bundle"
    - Images are cached upon the first build, will only update if changes are made then after for faster builds
    - Uses the Rollbar Error reporting service to push errors to a Rollbar project, can be disabled.
    - dependencies needed from Node are moved into /vendor/ folder

\[javascript\]
/\*\*
 \* Created by Alexander Romano on 02/05/2017.
 \* Front-End DevOps - Automate using GulpJS
 \*
 \* A little dependant heavy, but not without purpose...
 \*/

// Assigning modules to local variables
var gulp = require('gulp');
var less = require('gulp-less');
var syncDocs = require('browser-sync').create();
var browserSync = require('browser-sync').create();
var header = require('gulp-header');
var cleanCSS = require('gulp-clean-css');
var rename = require("gulp-rename");
var pkg = require('./package.json');
var merge = require('merge-stream');
var connect = require('gulp-connect');
var useref = require('gulp-useref');
var uglify = require('gulp-uglify');
var gulpIf = require('gulp-if');
var cssnano = require('gulp-cssnano');
var runSequence = require('run-sequence');
var imagemin = require('gulp-imagemin');
var cache = require('gulp-cache');
var del = require('del');
var sourcemaps = require('gulp-sourcemaps');

// Sets Up Rollbar Error Reporting
// Get a free account at https://rollbar.com/signup/
var rollbar = require('gulp-rollbar');
// Make sure to get your Token and Version from Rollbar account first
// Paste in the values for the specific project
var rollbarToken = "###";
var rollbarVersion = "###";
// Set Production URL for Rollbar
var rollbarURL = "https://projectname.netlify.com";

// Set banner content
var banner = \['/\*!\\n',
    ' \* Virtually(Creative) - &amp;amp;lt;%= pkg.title %&amp;amp;gt; v&amp;amp;lt;%= pkg.version %&amp;amp;gt; (&amp;amp;lt;%= pkg.homepage %&amp;amp;gt;)\\n',
    ' \* Copyright ' + (new Date()).getFullYear(), ' &amp;amp;lt;%= pkg.author %&amp;amp;gt;\\n',
    ' \* Licensed under &amp;amp;lt;%= pkg.license.type %&amp;amp;gt; (&amp;amp;lt;%= pkg.license.url %&amp;amp;gt;)\\n',
    ' \*/\\n',
    ''
\].join('');

/\*\*
 \* BROWSER SYNC
 \*/
// Starts BrowserSync on the Compiled Dev Folder (APP)
gulp.task('browserSync:dev', function () {
    browserSync.init({
        server: {
            baseDir: 'app'
        },
    });
});

// Starts BrowserSync on the Compiled Dev Folder (DEMO)
gulp.task('browserSync:demo', function () {
    browserSync.init({
        server: {
            baseDir: 'demo'
        },
    });
});

/\*\*
 \* USEREF
 \*/
// Starts the DEV concat of all JS/CSS wrapped in Build Comments
// Pushes errors to Rollbar service to monitor during development
// Dumps the results in DEMO folder
gulp.task('useref:dev', function () {
    return gulp.src('app/\*.html')
        .pipe(useref())
        .pipe(sourcemaps.init())
        .pipe(sourcemaps.identityMap())
        .pipe(gulpIf('app/js/\*.js', uglify()))
        .pipe(rollbar({
            accessToken: rollbarToken,
            version: rollbarVersion,
            sourceMappingURLPrefix: 'http://localhost:3000'
        }))
        .pipe(gulpIf('app/css/\*.css', cssnano()))
        .pipe(gulp.dest('demo/'));
});

// Starts the PROD concat of all JS/CSS wrapped in Build Comments
// Pushes errors to Rollbar service to monitor during production
// Dumps the results in the DIST folder
gulp.task('useref:prod', function () {
    return gulp.src('app/\*.html')
        .pipe(useref())
        .pipe(sourcemaps.init())
        .pipe(sourcemaps.identityMap())
        .pipe(gulpIf('app/js/\*.js', uglify()))
        .pipe(rollbar({
            accessToken: rollbarToken,
            version: rollbarVersion,
            sourceMappingURLPrefix: rollbarURL
        }))
        .pipe(gulpIf('app/css/\*.css', cssnano()))
        .pipe(gulp.dest('dist/'));
});

/\*\*
 \* IMAGE OPTIMIZATION &amp;amp;amp; CACHING
 \*/
// Finds and optimizes all images and caches results
// Only need to redo cache if new images are added after build
gulp.task('images:dev', function () {
    return gulp.src('app/img/\*\*/\*.+(png|jpg|jpeg|gif|svg)')
        // Caching images that ran through imagemin
        .pipe(cache(imagemin({
            interlaced: true
        })))
        .pipe(gulp.dest('demo/img'));
});

// Finds and optimizes all images and caches results
// Only need to redo cache if new images are added after build
gulp.task('images:prod', function () {
    return gulp.src('app/img/\*\*/\*.+(png|jpg|jpeg|gif|svg)')
        // Caching images that ran through imagemin
        .pipe(cache(imagemin({
            interlaced: true
        })))
        .pipe(gulp.dest('dist/img'));
});

/\*\*
 \* ASSET COPIES
 \* FONTS &amp;amp;amp; VIDEOS
 \*/

// Copies font's to DEMO folder
gulp.task('fonts:dev', function () {
    return gulp.src('app/fonts/\*\*/\*')
        .pipe(gulp.dest('demo/fonts'));
});

// Copies fonts to dist folder
gulp.task('fonts:prod', function () {
    return gulp.src('app/fonts/\*\*/\*')
        .pipe(gulp.dest('dist/fonts'));
});

// Copies vids (if any) to demo folder
gulp.task('vids:dev', function () {
    return gulp.src('app/vids/\*\*/\*')
        .pipe(gulp.dest('demo/vids'));
});

// Copies vids (if any) to dist folder
gulp.task('vids:prod', function () {
    return gulp.src('app/vids/\*\*/\*')
        .pipe(gulp.dest('dist/vids'));
});

/\*\*
 \* DEPENDANTS (NPM / BOWER)
 \*/

/\*\*
 \* CLEAN (Delete)
 \*/
// Cleans DIST folder
gulp.task('clean:prod', function () {
    return del.sync('dist');
});

// Cleans DEMO folder
gulp.task('clean:demo', function () {
    return del.sync('demo');
});

/\*\*
 \* MAIN BUILD TASKS
 \*/

// Main Dev task
// Runs Browser Sync with Watcher
gulp.task('dev', \['browserSync:dev'\], function () {
    // Reloads the browser whenever HTML or JS files change
    gulp.watch('app/\*.html', browserSync.reload);
    gulp.watch('app/js/\*\*/\*.js', browserSync.reload);
    gulp.watch('app/css/\*\*/\*.css', browserSync.reload);
});

// Main DEMO task
// Runs Browser Sync with Watcher
gulp.task('demo', \['browserSync:demo'\], function () {
    // Reloads the browser whenever HTML or JS files change
    gulp.watch('demo/\*.html', browserSync.reload);
    gulp.watch('demo/js/\*\*/\*.js', browserSync.reload);
    gulp.watch('demo/css/\*\*/\*.css', browserSync.reload);
});

// Main Dev Build task
// Builds Demo Folder by running all :dev tasks
gulp.task('demo:build', function (callback) {
    runSequence('clean:demo',
        \['useref:dev', 'fonts:dev', 'vids:dev', 'default'\], 'images:dev', 'demo',
        callback
    );
});

// Main PROD Build task
// Builds Dist folder by running all :prod tasks
gulp.task('prod:build', function (callback) {
    runSequence('clean:prod',
        \['useref:prod', 'fonts:prod', 'vids:prod', 'default'\], 'images:prod',
        callback
    );
});

// Default PROD Build task
// Builds Dist folder by running all :prod tasks
// typically invoked during an automated deployment
// Default task
gulp.task('default', \['prod:build'\]);
// Default "build" task
gulp.task('build', function (callback) {
    runSequence('prod:build', callback);
});

// Less task to compile the less files and add the banner
gulp.task('less', function () {
    return gulp.src('app/less/\*.less')
        .pipe(less())
        .pipe(header(banner, {
            pkg: pkg
        }))
        .pipe(gulp.dest('css'))
        .pipe(browserSync.reload({
            stream: true
        }));
});

// Minify CSS
gulp.task('minify-css', function () {
    var vCBP = gulp.src('app/css/\*.css')
        .pipe(cleanCSS({
            compatibility: 'ie8'
        }))
        .pipe(rename({
            suffix: '.min'
        }))
        .pipe(gulp.dest('css'))
        .pipe(browserSync.reload({
            stream: true
        }));

    var vCVS = gulp.src('vendor/\*/css/\*.css')
        .pipe(cleanCSS({
            compatibility: 'ie8'
        }))
        .pipe(rename({
            suffix: '.min'
        }))
        .pipe(gulp.dest('css'))
        .pipe(browserSync.reload({
            stream: true
        }));

    return merge(vCBP, vCVS);
});

// Minify JS
gulp.task('minify-js', function () {
    var vCBPjs = gulp.src('app/js/\*.js')
        .pipe(uglify())
        .pipe(header(banner, {
            pkg: pkg
        }))
        .pipe(rename({
            suffix: '.min'
        }))
        .pipe(gulp.dest('js'))
        .pipe(browserSync.reload({
            stream: true
        }));

    var vCVendorjs = gulp.src('vendor/\*/scripts/\*.js')
        .pipe(uglify())
        .pipe(header(banner, {
            pkg: pkg
        }))
        .pipe(rename({
            suffix: '.min'
        }))
        .pipe(gulp.dest('js'))
        .pipe(browserSync.reload({
            stream: true
        }));

    return merge(vCBPjs, vCVendorjs);
});

// Copy Bootstrap core files from node\_modules to vendor directory
gulp.task('bootstrap', function () {
    return gulp.src(\['node\_modules/bootstrap/dist/\*\*/\*', '!\*\*/npm.js', '!\*\*/bootstrap-theme.\*', '!\*\*/\*.map'\])
        .pipe(gulp.dest('vendor/bootstrap'));
});

// Copy jQuery core files from node\_modules to vendor directory
gulp.task('jquery', function () {
    return gulp.src(\['node\_modules/jquery/dist/jquery.js', 'node\_modules/jquery/dist/jquery.min.js'\])
        .pipe(gulp.dest('vendor/jquery'));
});

// Copy Magnific Popup core files from node\_modules to vendor directory
gulp.task('magnific-popup', function () {
    return gulp.src(\['node\_modules/magnific-popup/dist/\*'\])
        .pipe(gulp.dest('vendor/magnific-popup'));
});

// Copy ScrollReveal JS core JavaScript files from node\_modules
gulp.task('scrollreveal', function () {
    return gulp.src(\['node\_modules/scrollreveal/dist/\*.js'\])
        .pipe(gulp.dest('vendor/scrollreveal'));
});

// Copy Font Awesome core files from node\_modules to vendor directory
gulp.task('fontawesome', function () {
    return gulp.src(\[
            'node\_modules/font-awesome/\*\*',
            '!node\_modules/font-awesome/\*\*/\*.map',
            '!node\_modules/font-awesome/.npmignore',
            '!node\_modules/font-awesome/\*.txt',
            '!node\_modules/font-awesome/\*.md',
            '!node\_modules/font-awesome/\*.json'
        \])
        .pipe(gulp.dest('vendor/font-awesome'));
});

// Copy all dependencies from node\_modules
gulp.task('copy', \['bootstrap', 'jquery', 'fontawesome', 'magnific-popup', 'scrollreveal'\]);

// Create browserSync task for Docs
gulp.task('syncDocs', function () {
    browserSync.init({
        server: {
            baseDir: 'docs/'
        }
    });
});

// Watch Task that watches for HTML/JS changes in Docs folder and reloads BrowserSync
gulp.task('docs', \['syncDocs'\], function () {
    // Reloads the browser whenever HTML or JS files change
    gulp.watch('\*.html', syncDocs.reload);
    gulp.watch('assets/\*.js', syncDocs.reload);
    gulp.watch('assets/\*.css', syncDocs.reload);
});
\[/javascript\]
