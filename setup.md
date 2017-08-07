---
layout: page
title: Setup
permalink: /setup/
---

This setup guide is for deploying to Github-pages. This is a very specific method, and if you're looking for a more general setup guide, check out [this guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).

The easiest method is to simply [fork this repo](https://github.com/brettinternet/minimaless#fork-destination-box){:target="_blank"}<i class="fa fa-external-link"></i>.
Then, edit the files you'd like.
Because Github doesn't allow automated builds from custom Jekyll themes, there's another simple work around illustrated here.

I prefer the following unique method because using `bundle update` to update the gems is a simple task. I use [Travis CI](https://travis-ci.org) to build from a Rakefile similar to Github's Rakefile for building Github-pages sites.
Similar upgrading can be performed from upstream if you choose to fork the theme [using git](https://mmistakes.github.io/minimal-mistakes/docs/upgrading/#use-git).

1. [Install Jekyll](https://jekyllrb.com/docs/quickstart/)
2. Create a new Jekyll project with
```
jekyll new <your-project-name>
```
3. Edit the `Gemfile` and replace the line indicating the default theme:
```yml
gem "minimaless"
```
4. Run `bundle install` to install minimaless
5. Add the following files to app's root-level folder:
    1. Add an `index.md` file with the following header:
        ```yml
        ---
        layout: about
        ---
        ```
    2. Add `blog.md`:
        ```yml
        ---
        layout: blog
        title: Blog
        permalink: /blog/
        ---
        ```
    3. Add `contact.md`:
        ```yml
        ---
        layout: contact
        title: Contact
        permalink: /contact/
        ---
        ```
6. Copy the project's [`_config.yml`](https://github.com/brettinternet/minimaless/blob/master/_config.yml) and paste it over the existing config file. Replace the variable definitions to customize your site.
7. Include a description of yourself or the site in the `index.md`.
8. Create a directory called `assets/` and add a `logo.svg` (or any vector/image file extension you prefer) and a `favicon.png` for your site.
9. Copy the [Rakefile](https://github.com/brettinternet/minimaless/blob/master/Rakefile) and Rakefile configuration settings at the bottom of `_config.yml`.
    1. Change these variables to match your own settings.
    2. Add your encrypted GH token (notes on how to encrypt are commented in the `.travis.yml`).
10. Turn on building in Travis CI for your site's repo. Then, push your site's source code to a new branch called `source` and the build should trigger and run the Rakefile.
    - Instead of using Travis CI to build your site remotely when you push, you could also build your site locally and push your site to a separate `gh-pages` branch by [following these instructions](https://gist.github.com/cobyism/4730490).
11. You may consider using something like [prose.io](http://prose.io) to manage your blog posts from the web.

