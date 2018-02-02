# Changelog
All notable changes to this project will be documented here.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## 0.0.13 // 2017-2-2
### Added
- Additional whitespace above `h1` and `h2` tags
- Tags page and clickable tagging navigation (see the [Features & Setup](/_pages/setup.md) page for more information)

### Removed
- Removed links page

## 0.0.12 // 2017-12-12
### Fixed
- Footer icons vertical alignment
- Other minor CSS fixes

### Added
- PayPal icon in contact

## 0.0.11 // 2017-08-19
### Fixed
- Fixed footer align left for palm devices
- H1 font fixed
- Fixed post `<a>` to be more distinct from `<strong>` text


## 0.0.10 // 2017-08-19
### Fixed
- minor CSS fixes

## 0.0.9 // 2017-08-19
### Fixed
- set jekyll production environment in Rakefile build
- Blog post pagination

## 0.0.8 // 2017-08-19
### Changed
- Changed front page back to blog, and /about/ to the landing page
- Allow user to set page title case

### Added
- Added splash page and links page

### Fixed
- Fixed keybase icon hover
- Fixed `header_pages` settings specification in config

## 0.0.7 // 2017-08-06
### Added
- Created splash page for single page sites or immersive intro without header/footer

## 0.0.6 // 2017-08-04
### Added
- Custom `.travis.yml` for remote building
- Rakefile for building to separate branch and travis ci hook

## 0.0.5 // 2017-08-02
### Added
- CSS support for external link icons with `<i class="fa fa-external-link"></i>`
- Other minor styling

## 0.0.3 // 2017-08-01
### Changed
- Minor CSS edits to enhance neatness and simplicity

### Added
- Screenshot of blog page added
- Created a very simple setup guide for new users

## 0.0.2 // 2017-07-31
### Added
- Additional feature specifications in README.md
- Users only have to add an `.asc` file to their static files for GPG download link to appear
- Added Jekyll-feed for `.xml` generation for blog entries

### Fixed
- Made site logo and gpg key paths relative
- Corrected logo logic to show sitename is `logo.*` doesn't exist in `/assets/`

## 0.0.1 // 2017-07-30
### Added
- Initial fork from Minima
- Initial setup change including basic styling, social icons, logo, header and footer
