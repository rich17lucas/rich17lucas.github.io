---
layout: post
title:  "Notes about using Jekyll"
date:   2020-03-24 07:45:00 +0000
categories: jekyll update
---
# How to install Jekyll
### Requirements
For Windows 10 read the [Jekyllrb.com](https://jekyllrb.com/docs/installation/windows/) pages. These cover how to install it for Windows and also how to use the Windows Sub-system for Linux (WSL) using BASH.


For Ubuntu read [Ubuntu Installation](https://jekyllrb.com/docs/installation/ubuntu/)

For other Linux distros: [Jekyll on Linux](https://jekyllrb.com/docs/installation/other-linux/)

And not forgetting macOS [Jekyll on macOS](https://jekyllrb.com/docs/installation/macos/)

# How to create a site with Jekyll
* Change to the directory where you will work on your site.
* Create the the Jekyll site:

```jekyll new mynewsite```

# How to start the local Jekyll server

* Change to the ```mynewsite``` directory:

```cd mynewsite```

* Start the Jekyll server so that you can develop and publish the site locally 

```bundle exec jekyll serve```

* Open a web browser and go to page [http://localhost:4000](http://localhost:4000)
