---
layout: page
title: Setup
permalink: /setup/
---

1. [Install Jekyll](https://jekyllrb.com/docs/quickstart/)
2. Create a new Jekyll project with
```
jekyll new <your-project-name>
```
3. Edit the `Gemfile` and replace the line indicating the default theme with:
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
6. [Copy the project's](https://github.com/brettinternet/minimaless/blob/master/_config.yml) `_config.yml` and paste it over the existing config file. Replace the variable definitions to customize your site.
7. Include a description of yourself or the site in the `index.md`.
8. Create a directory called `assets/` and add a `logo.svg` (or any vector/image file extension you prefer) and a `favicon.png` for your site
9. You may consider using something like [Prose.io](http://prose.io) to manage your blog posts from the web
