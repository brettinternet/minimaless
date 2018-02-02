---
layout: page
title: Features & Setup
permalink: /setup/
---

# Features

- Blog in markdown using [Jekyll](jekyllrb.com)!
- Include any Font Awesome icon <i class="fa fa-check-square"></i>
```html
<i class="fa fa-check-square"></i>
```
- Use icons and other HTML mixed with your markdown
  (ex: [external link<i class="fa fa-external-link"></i>](https://google.com){:target="\_blank"})
```
[external link<i class="fa fa-external-link"></i>](https://google.com){:target="_blank"}
```
- Use a [splash page]({{site.baseurl}}/splash/) with no header or footer
- Include a preview of posts or not with `preview_posts: true`
- Change the number of posts on each page with `paginate` in the config
- [List entries by tag]({{site.baseurl}}/tags/) (see setup below to learn how to setup tag pages)




# Setup

## Deploy
This setup guide is for deploying to Github-pages. This is a very specific method, and if you're looking for a more general setup guide, check out [this guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).

Now that GitHub does build custom Jekyll themes, you can simply add `remote_theme: brettinternet/minimaless` to the `_config.yml` file.
Consult GitHub [blog post](https://github.com/blog/2464-use-any-theme-with-github-pages) on the topic for more information.
The easiest method is to simply [fork this repo](https://github.com/brettinternet/minimaless#fork-destination-box){:target="\_blank"}<i class="fa fa-external-link"></i>.
Then, edit the files you'd like.
Because Github ~~doesn't allow~~ used to not allow automated builds from custom Jekyll themes, there's another simple work around illustrated below.

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
    - Add an `index.md` file with the following header:
        ```yml
        ---
        layout: about
        ---
        ```
    - Add `blog.md`:
        ```yml
        ---
        layout: blog
        title: Blog
        permalink: /blog/
        ---
        ```
    - Add `contact.md`:
        ```yml
        ---
        layout: contact
        title: Contact
        permalink: /contact/
        ---
        ```
6. [Copy](https://github.com/brettinternet/minimaless/blob/master/_config.yml) the project's `_config.yml` and paste it over the existing config file. Replace the variable definitions to customize your site.
7. Include a description of yourself or the site in the `index.md`.
8. Create a directory called `assets/` and add a `logo.svg` (or any vector/image file extension you prefer) and a `favicon.png` for your site.
9. Copy the [Rakefile](https://github.com/brettinternet/minimaless/blob/master/Rakefile) and Rakefile configuration settings at the bottom of `_config.yml`.
    1. Change these variables to match your own settings.
    2. Add your encrypted GH token (notes on how to encrypt are commented in the `.travis.yml`).
    3. Add `gem 'rake', '12.0.0'` to your `Gemfile`.
10. Turn on building in Travis CI for your site's repo. Then, push your site's source code to a new branch called `source` and the build should trigger and run the Rakefile. Once the build is push to `master`, Travis CI may attempt to build the master repo (and fail) unless you select the option to only run Travis CI when a `.travis.yml` is present.
    - Instead of using Travis CI to build your site remotely when you push, you could also build your site locally and push your site to a separate `gh-pages` branch by [following these instructions](https://gist.github.com/cobyism/4730490).
11. You may consider using something like [prose.io](http://prose.io) to manage your blog posts from the web.



## Tags

Make a new folder called `tag` where you will add markdown files for each new tag you use on your site.

```
minimaless
├─ tag
│  └─ kittens.md
└─ _posts
```

Create a new markdown file with the tag as the file name (eg. `<tag name>.md`). You only need to set up the header information. For example, if the tag is `kittens`, then use the following header:

```yml
---
layout: tags
tag: kittens
permalink: /tag/kittens/
---
```

This must be done for every new tag you create. This is the page that users will see when they click on a tag. [View the tag page here]({{site.baseurl}}/tags/).
