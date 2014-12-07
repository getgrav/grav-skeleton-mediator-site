---
title:  "Mediator Theme Setup"
slug: theme-setup
date:   02/05/2014
taxonomy:
    tag: [sample post, featured, installation]
image: tools.jpg
---

# Mediator Origins

The Mediator theme for Grav is a direct port of the [Mediator Theme for Jekyll](https://github.com/dirkfabisch/mediator) designed by [Dirk Fabisch](http://blog.base68.com/about/) which in turn was inspired by the [Readium 2.0 Theme for Ghost](http://www.svenread.com/readium-ghost-theme/).

A couple of minor tweaks and adjustments have been made to better take advantage of Grav features and functionality.

# Features

* Fully Responsive layout
* Use header images in articles, if you want to (add tag "image" and url to the image in the front matter section of a post)
* Minimal design
* Featured article support
* FontAwesome implemented for easy use of icons fonts
* Free & Open Source Font usage

## Basic Setup for a new Grav site

The simplest way to install Mediator theme for Grav is to download and install the Mediator Skeleton package:

1. [Download Mediator Skeleton](http://getgrav.org/downloads/skeletons#extras)
2. Simply unzip the package into your web root folder.
3. Point your browser at the folder, job done!

**TIP:** Check out the [general Grav installation instructions](http://learn.getgrav.org/basics/installation) for more details on this process.

---

## Existing Grav site

It is possible to install just the theme, but page content will need to reference the Mediator theme's supported templates.  It is strongly advised to at least install the Mediator Skeleton package to see the theme's capabilities in action.

To install  **just** the theme:

```
$ bin/gpm install mediator
```

---

## Advanced GitHub-based installation

1. Download and install [Grav](https://github.com/getgrav/grav)
2. Create a new sandbox site with: `bin/grav sandbox ~/public_html/mediator`
3. Clone this repo into the `mediator` folder as `user`: `git clone: https://github.com/getgrav/grav-skeleton-mediator-site ~/public_html/mediator/user`
4. Install the plugin and theme dependencies: `bin/grav install`

# Configuration

Most of the configuration of the theme is done in the `user/config/site.yaml` file:

```
title: Mediator
description: A Grav theme - Medium inspired
taxonomies: [tag, featured]
metadata:
    description: Grav is an easy to use, yet powerful, open source flat-file CMS

logo: /user/images/logo.jpg

date_long: 'd F Y'
date_short: 'd M Y'

author:
    name: Bill Bloggs
    email: a-mail@mail.mail
    image: /user/images/avatar.jpg
    bio: I'm a blogger and a Grav-lover

social:
    - icon: twitter
      url: https://twitter.com/getgrav
      desc: Follow me on twitter
      share_url: http://twitter.com/share
      share_title: ?text=
      share_link: "&amp;url="

    - icon:  facebook
      url:   https://facebook.com/???
      desc: Connect with me facebook
      share_url: //www.facebook.com/sharer.php
      share_title: ?t=
      share_link: "&amp;u="

    - icon: github
      url: https://github.com/getgrav
      desc: Fork me on github
      share_url:
      share_title:
      share_link:

    - icon:  google-plus
      url:   https://google.com/???
      desc:  Add me on google+
      share_url:
      share_title:
      share_link:
```

Main settings for the site

* **title**: name of your site
* **description**: description of your site

* **logo**: small logo for the site (300x * 300x)
* **long date**: date used in the `default` listing page
* **short date**: date used in the `post` details page

* **author name**: name site owner
* **author email**: mail address of the site owner
* **author image**: small image of author (300x * 300px)
* **author bio**: short one sentence biography

### Social

The template allows to add all major social platforms to your site.
Fill the the form for each platform. If you leave the share_* entries empty, the sharing buttons below a post are not shown.  If you leave the **url** and **desc** empty the icons are not shown on the index page, but the share icons on the article pages remains untouched (Thanks to [Phil](https://github.com/philsturgeon))

* **icon**: name of social platform (must match a name of [font-awsome](http://fortawesome.github.io/Font-Awesome/) icon set )
* **url**:  url of your account
* **desc**: slogan of the platform
* **share_url**: share url
* **share_title**: first part of url for the title
* **share_link**: second part of the share url for the link to the post

The Twig template engine will magical combine the different parts to a share url.

```
http://twitter.com/share?text=post_title&amp;url=post_url
````

# Supported Page Types

The Mediator theme supports 3 page types via templates:

* **default**: the template used to display the default blog listing view
* **post**: a full page of the blog post
* **page**: similar to the post, but without author information or reading-time

# Licensing

[MIT](https://github.com/dirkfabisch/madiator/blob/master/LICENSE) with no added caveats, so feel free to use this on your site without linking back to me or using a disclaimer or anything silly like that.
