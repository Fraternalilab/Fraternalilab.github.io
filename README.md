# Fraternalilab group website

Uses [Minimal Mistakes Jekyll theme](https://mmistakes.github.io/minimal-mistakes/).

Developed by Joseph Ng, Jan/Feb 2021

Website accessible by <https://Fraternalilab.github.io> . Redirection from KCL website to be set up in due course.

## Update content online

All pages/posts are written in markdown format. [This](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) is a nice cheat-sheet on how to format text in markdown.

To add pages/posts, use any one of the existing pages/posts as templates and modify.

* **Pages**: each main page of the website (accessible from menu bar at the top of the page) - i.e. 'People', 'Software' etc. All `.md` files in `_pages` directory.
* **Posts**: news updates (accessible from the bottom menu on the index page). All `.md` files in `_posts` directory.
* `assets` contain images and files. Images to be shown on pages/posts in the `images` subfolder; downloadable files in `downloads`. You can reference these files using paths relative to the root of this repository (i.e. location of this README), like this: `assets/images/example.png`. See examples in any pages/posts that include an image / a download link.

## Update content offline

This site was originally developed inside a docker container. All docker set up are available in the repo and follows this site: [here](https://www.cross-validated.com/Personal-website-with-Minimal-Mistakes-Jekyll-Theme-HOWTO-Part-I/).
