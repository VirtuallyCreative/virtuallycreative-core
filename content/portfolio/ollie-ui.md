---
title: Ollie-UI
subtitle: open-source | starter-kit
date: '2020-05-08'
thumb_image: images/Home-Ollie-UI-Starter-Kit-Documentation.png
thumb_image_alt: Ollie-Ui starter kit documentation site home page
sections:
  - type: text_section
    content: >
      [Ollie-UI](https://ollie-ui.dev) is a culmination of ~50 front-end
      developer decisions typically made when starting a new project, so to
      never repeat myself going forward
      ([DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)) I've
      bundled these decisions together into this starter-kit and thought I'd
      [open-source these
      decisions](https://github.com/VirtuallyCreative/ollie-ui) to help others,
      receive feedback and we can all improve together!
  - type: image_section
    image_alt: Ollie-Ui Documentation Site Homepage
    caption: Ollie-Ui Documentation Site Homepage
    width: wide
    image: images/ollie-ui-doc-site-homepage.jpg
  - type: text_section
    content: "## Why Ollie\n\nLots of decisions can go into a boilerplate - so after making these decisions over and over they're now baked into this JavaScript Stater Kit.\n\nSome of the things out of the box are,\n\n*   **Webpack Devel­op­ment / Pro­duc­tion**\_ —  Sep­a­rate dev and prod con­figs & builds. Local devel­op­ment means fast builds via the in-mem­o­ry web­pack-dev-serv­er, and for pro­duc­tion builds every pos­si­ble opti­miza­tion needs to be utilized, making for slower builds at the gain of better optimizations.\n\n*   **Hot Mod­ule Replace­ment**\_ —  as changes are made to JavaScript, CSS, or tem­plates, the web­page seam­less­ly refreshes.\n\n*   **Dynam­ic Code Split­ting**  —  Webpack sorts out how to chunk JavaScript in a con­fig file, auto-magically.\n\n*   **Async Dynam­ic Mod­ule Load­ing**\_- Load only the code/​resources need­ed, when they are need­ed, with­out ren­der blocking.\n\n*   **Mod­ern to Lega­cy JS Bun­dles**\_—  Deploy mod­ern ES2019+ JavaScript mod­ules while grace­ful­ly pro­vid­ing a fall­back lega­cy bun­dle for lega­cy browsers (with all of the tran­spiled code and polyfills).\n\n*   **Cache Bust­ing via manifest.json**\_- Sets long expiry data for our sta­t­ic assets, while also ensur­ing that they are auto­mat­i­cal­ly cache bust­ed if they change.\n\n*   **Crit­i­cal CSS**\_ —  This is some­thing that makes ini­tial page loads sig­nif­i­cant­ly faster by only delivering the styles needed first.\n\n*   **Work­box Ser­vice Work­er**\_ —  Lever­age Google’s Work­box project to gen­er­ate a Ser­vice Work­er for us that will know about all of our project’s assets.\n\n*   **PostC­SS**\_—  The ​“Babel of CSS”, lets you SASS like a boss.\n\n*   **Image Opti­miza­tion**\_ —  Opti­mize them via auto­mat­ed tools like mozjpeg, optipng, svgo, etc for next step...\n\n*   **Auto­mat­ic .webp Cre­ation**\_ —  Chrome, Edge, and Fire­fox all are sup­port­ing .webp, and can signifigantly boost performance.\n"
seo:
  title: Design Is One
  description: This is the sample project description
  extra:
    - name: 'og:type'
      value: website
      keyName: property
    - name: 'og:title'
      value: Design Is One
      keyName: property
    - name: 'og:description'
      value: This is the sample project description
      keyName: property
    - name: 'og:image'
      value: images/work-poster-1.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: Design Is One
    - name: 'twitter:description'
      value: This is the sample project description
    - name: 'twitter:image'
      value: images/work-poster-1.jpg
      relativeUrl: true
layout: project
---
