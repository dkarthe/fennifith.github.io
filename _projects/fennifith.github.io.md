---
layout: project
type: website
title: "fennifith.github.io"
description: "My personal website."
repo: fennifith/fennifith.github.io
git: git://github.com/fennifith/fennifith.github.io.git
links:
  - name: GitHub
    url: https://github.com/fennifith/fennifith.github.io
    icon: https://github.com/favicon.ico
  - name: Issues
    url: https://github.com/fennifith/fennifith.github.io/issues
    icon: /images/ic/bug.svg
  - name: Website
    url: https://jfenn.me/
    icon: https://jfenn.me/images/favicon-32.ico
contributors:
  - login: fennifith
    avatar: https://avatars1.githubusercontent.com/u/13000407?v=4
    url: https://github.com/fennifith
  - login: crutchcorn
    avatar: https://avatars0.githubusercontent.com/u/9100169?v=4
    url: https://github.com/crutchcorn
  - login: jacksonhvisuals
    avatar: https://avatars0.githubusercontent.com/u/29767267?v=4
    url: https://github.com/jacksonhvisuals
  - login: x4m3
    avatar: https://avatars3.githubusercontent.com/u/8809909?v=4
    url: https://github.com/x4m3
isDocs: false
isWiki: false
languages:
  - HTML
  - JavaScript
  - CSS
  - Shell
  - Ruby
pushed: 2018-11-22T19:10:59Z
---

This is a website that displays all of my current projects and applications. As [client-side JavaScript is bad](https://jfenn.me/blog/2018-08-19-Client-Side-JavaScript/), it is now written mostly in [Jekyll](https://jekyllrb.com/). It does not update its content automatically, but there is [this Node.js script](https://github.com/fennifith/fennifith.github.io/blob/master/./scripts/update.js) and [a shell script](https://github.com/fennifith/fennifith.github.io/blob/master/./scripts/update.sh) that may be used to update it periodically.

[![Build Status](https://travis-ci.com/fennifith/fennifith.github.io.svg?branch=master)](https://travis-ci.com/fennifith/fennifith.github.io)

## Building

After cloning the project, run `git submodule init` and `git submodule update` in the root directory to fetch the project's [CSS styles](https://jfenn.me/redirects/?t=github&d=styles), which are stored in a separate repository to simplify versioning (different parts of my site use different versions of the css, so I don't have to worry about things breaking immediately if I change something).

Once this is done, you can run `jekyll build` to generate the HTML (storing it in "_site/"), or `jekyll serve` to start a server so that you can view the site in a browser.

## License

As this is my _personal_ site, I have some issues with placing the whole thing under a license for public use. However, I am trying to split it into parts so that I can open-source projects such as [bugiver](https://jfenn.me/projects/bugiver) and [photos](https://jfenn.me/projects/photos) separately. To clarify, I have no problem with borrowing small snippets from this repository for use in other projects, I am only trying to prevent people from just changing the text and claiming this entire project as their own.

If you want a template to use for your own portfolio and do not want to put in the time to write it yourself, I recommend using something like [quicksilver](https://github.com/jacksonhvisuals/quicksilver) instead. For inspiration designing your own, see [personalsit.es](https://personalsit.es/) for a list of random people's websites.

## Contributing

Pull requests / issue reports are welcome. Feel free to contact me before working on any significant changes (in fact, please do; I would prefer not to have to turn down a contribution because I don't agree with it - that would just be a waste of time and effort on the contributor's side).
