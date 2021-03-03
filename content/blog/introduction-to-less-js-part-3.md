---
title: Introduction to LESS.js -Part 3
subtitle: A interesting tale about function of design
excerpt: >-
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor
  incididunt ut labore et dolore magna aliqua.
date: '2011-05-17'
thumb_image: images/lessLgImg.png
thumb_image_alt: White concrete building wall
image: images/lessLgImg.png
image_alt: White concrete building wall
seo:
  title: Introduction to LESS.js -Part 3
  description: >-
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Introduction to LESS.js -Part 3
      keyName: property
    - name: 'og:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
      keyName: property
    - name: 'og:image'
      value: images/lessLgImg.png
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Introduction to LESS.js -Part 3
    - name: 'twitter:description'
      value: >-
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore
    - name: 'twitter:image'
      value: images/lessLgImg.png
      relativeUrl: true
layout: post
---

## Using LESS #4: "Live Refresh"

This is our last topic we're going to cover in this tutorial and is a litte known function of LESS. You can make the browser refresh automatically (locally) without having to continually hit the refresh button while styling! All you need to do is add: \[javascript\]<script><br /> less.env = 'development';<br /> less.watch();<br /> </script> \[/javascript\] To your HTML markup just before the closing html tag, refresh the page and that's it! Now your page will refresh anytime you make a change live to style.less! Pretty cool huh? Make sure you **TAKE THIS OFF** before you deploy your solution though! Great for development, **not** for live usage.

### Final Thoughts:

I hope you've enjoyed this introduction to the LESS.js Libary and what it can do to extend the functionality of your CSS markup. I hope to see many sites in the future using this moving forward to bring complex CSS and creative design styles to life!

This is what your final HTML and CSS markup should look like.

#### HTML MARKUP:

\[html\]

<meta charset="UTF-8"> <title>LESS.js Tutorial</title> <!-- LESS Stylesheet --> <link rel="stylesheet/less" type="text/css" href="css/style.less">

<!-- LESS Javascript --> <script src="http://lesscss.googlecode.com/files/less-1.0.41.min.js"></script> <div id="header"> <h2>A Headline</h2> This is some text with an <a href="#">anchor</a> present.

</div> <!-- /header --> <div id="footer"> <a href="#">Link Name</a></div> <!-- /footer -->

<!-- Dev Purposes Only --> <script><br /> less.env = 'development';<br /> less.watch();<br /> </script>

\[/html\]

#### CSS MARKUP:

\[css\]@color: #FFFFFF; @footcolour: #000000;

body { background-color: @footcolour; }

#header { background-color: #000000; }

h2 { color: @color; }

#header { h2 { font-size: 26px; font-weight: bold; } //Close h2 p { font-size: 12px; color: @color; a { text-decoration: none; &amp;:hover { border-width: 1px } //Close :hover } //Close a } //Close p } //Close #header

// Create Mixin .rounded-corners and assign a @radius variable to pass through

.rounded-corners (@radius: 5px) { border-radius: @radius; -webkit-border-radius: @radius; -moz-border-radius: @radius; }

#header { .rounded-corners; } #footer { background-colour: @footcolour; .rounded-corners(10px); }

\[/css\] Enjoy LESS/CSS and happy coding!

### P.S. The Mobile "Hack"

What, you thought I forgot?! Ha!

So, you want to use LESS but you're thinking of doing going mobile friendly; or you have a website already and want to make it compatible for mobile browsing?

Well, I'd start by telling you that using LESS would probably not be your best idea since you'll require JavaScript to be enabled by default on a mobile browser which means your limiting yourself to smartphone users only (not that 220 million users in North America alone is small, but you get the point) if you're trying to maximize accessibility.

If you have a website that has a re-direct via some type of CSS/Javascript media type detection, or redirect where it sends you to a whole separate sub-domain/site folder/something that doesn't require access to the original style-sheet of the main (or root) website then you could use LESS for your main site and just use an normal style-sheet for your mobile portal.

This second method is our "hack" which, to be honest isn't a hack at all really, just good ol' fashion copying the output of the style.less (from the browser, I used Firebug extension in Mozilla Firefox personally) and pasting into a fresh .css style-sheet on your mobile site. Then you can edit it down on your own to make it appropriate to display into mobile browsers as just pasting the output will give you exactly the same style-sheet as your main website, not a mobile portal.

Enjoy!
