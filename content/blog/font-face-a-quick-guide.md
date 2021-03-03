---
title: Font-Face - A Quick Guide
subtitle: A interesting tale about function of design
excerpt: >-
  @font-face is a CSS rule which allows you to show fonts on a Web page
date: '2011-05-17'
thumb_image: images/font-face-kit.png
thumb_image_alt: White concrete building wall
image: images/font-face-kit.png
image_alt: White concrete building wall
seo:
  title: Font-Face A Quick Guide
  description: >-
    @font-face is a CSS rule which allows you to show fonts on a Web page
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: Font-Face A Quick Guide
      keyName: property
    - name: 'og:description'
      value: >-
        @font-face is a CSS rule which allows you to show fonts on a Web page
      keyName: property
    - name: 'og:image'
      value: images/font-face-kit.png
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Font-Face A Quick Guide
    - name: 'twitter:description'
      value: >-
        @font-face is a CSS rule which allows you to show fonts on a Web page
    - name: 'twitter:image'
      value: images/font-face-kit.png
      relativeUrl: true
layout: post
---

@font-face is a CSS rule which allows you to show fonts on a Web page even if that font is not installed on the users' computer! This means that designers and developers don't have to use those horrible looking pre-installed fonts anymore! Freedom!
The best part is most of the hard work can be done for us! Thanks to an awesome website [Font Squirrel](http://www.fontsquirrel.com/fontface) you can get quick and easy access to 100's of commercial free fonts already packaged up in a nice little kit! For our example today we're going to use the ["Permanent-Marker" fontface kit](http://www.fontsquirrel.com/fontfacekit/permanent-marker) from Font Squirrel.

[](http://www.fontsquirrel.com "FontSquirrel")

#### Inside the Kit

Each @font-face font kit comes with:

- TrueType Fonts for Firefox 3.5+ , Opera 10+, Safari 3.1+, Chrome 4.0.249.4+
- EOT fonts for Internet Explorer 4+
- WOFF fonts for Firefox 3.6+, Internet Explorer 9+, Chrome 5+
- SVG fonts for iPad and iPhone
- Cufón fonts in case you want them
- Demo.html and stylesheet.css so you can get going fast

This is everything you'll need to use the awesome font you picked quickly and easily with (up to 92%) browser support!

\*\*\*NOTE: Fonts must have a Web-font licence! Check the Web site you are downloading or purchasing the font from, or the documentation that comes with the font. END NOTE\*\*\*

#### Lets Get Started: CSS

So if you open the fontkit given to us theirs a number of files inside. Don't worry if there is a lot going on I'll break it all down for you. First, let's open the .css file and see whats going on here.

\[html\]
&amp;amp;lt;br /&amp;amp;gt;/\* Generated by Font Squirrel (http://www.fontsquirrel.com) on April 3, 2011 11:55:32 PM America/New\_York \*/&amp;amp;lt;br /&amp;amp;gt;@font-face {&amp;amp;lt;br /&amp;amp;gt;font-family: 'PermanentMarkerRegular';&amp;amp;lt;br /&amp;amp;gt;src: url('PermanentMarker-webfont.eot');&amp;amp;lt;br /&amp;amp;gt;src: url('PermanentMarker-webfont.eot?iefix') format('eot'),&amp;amp;lt;br /&amp;amp;gt;url('PermanentMarker-webfont.woff') format('woff'),&amp;amp;lt;br /&amp;amp;gt;url('PermanentMarker-webfont.ttf') format('truetype'),&amp;amp;lt;br /&amp;amp;gt;url('PermanentMarker-webfont.svg#webfontCD2zZm7K') format('svg');&amp;amp;lt;br /&amp;amp;gt;font-weight: normal;&amp;amp;lt;br /&amp;amp;gt;font-style: normal;&amp;amp;lt;br /&amp;amp;gt;}&amp;amp;lt;br /&amp;amp;gt;
\[/html\]




So this is how we use @font-face. After declaring @font-face, we must name the font-family: this name can be anything you want and what you'll use to call the font when you need it for designing
in this case Font-Squirrel chose to call it "PermanetMarkerRegular". After font-family we need to link to the font files from the kit sort of like a background image the difference is we also declare the
format type afterward using format('###'), this is so each browser knows what font file to use to display the fonts.

The first src: url('') format(''); should always be the .eot font file. This file is for IE and is required first for IE to display the fonts propery, other browers arn't as picky (stupid IE) and because of that,
we can put their fonts after but you must use another src: url('') format(''); to list the rest of the browsers because IE want's to be in a statement all its own. What an attention hog.

#### Usage: HTML

So, you created your @font-face and now you're ready to start some CSS styling and inlcude this font into the design! But wait, we still need to add the font files to our project! If you look above
our url('') reference has no folders, which means the fonts should be in the same directory as the style.css file. If you wanted to put the fonts into a folder like "fonts" for example,
make sure you remember to update the paths url('fonts/PermanentMarker-webfont.eot');

The last thing is now using in your style! Just make sure you obviously reference your stylesheet in your html!

\[html\]&amp;amp;lt;br /&amp;amp;gt;&amp;amp;amp;amp;lt;link rel=&amp;amp;amp;amp;quot;stylesheet&amp;amp;amp;amp;quot; type=&amp;amp;amp;amp;quot;text/css&amp;amp;amp;amp;quot; href=&amp;amp;amp;amp;quot;style.css&amp;amp;amp;amp;quot; /&amp;amp;amp;amp;gt;&amp;amp;lt;br /&amp;amp;gt;\[/html\]




and then you can use:

\[css\]&amp;amp;lt;br /&amp;amp;gt;h1 {&amp;amp;lt;br /&amp;amp;gt;font-family: PermanentMarkerRegular, Helvetica, Arial, sans-serif;&amp;amp;lt;br /&amp;amp;gt;}&amp;amp;lt;br /&amp;amp;gt;\[/css\]




in your CSS with a couple of fall backs JUST in case @font-face isn't supported. A good designer should always add them. Thats it! You now are able to use @font-face in all your projects. Its so much easyer knowing that your fonts will display properly across most platforms. Enjoy!