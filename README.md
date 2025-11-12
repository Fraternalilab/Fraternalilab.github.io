# Fraternalilab group website

Uses [Minimal Mistakes Jekyll theme](https://mmistakes.github.io/minimal-mistakes/).

Developed by Joseph Ng, Jan/Feb 2021

Website accessible by <https://Fraternalilab.github.io> . Redirection from KCL website <http://fraternalilab.kcl.ac.uk>. This replace the old group website hosted in KCL servers.

## Log
* 12/11/2025: configured Github Actions to automatically rebuild the website every time new content is pushed. (JN)

## Structure
A number of folders here contain templates etc. that *do not need to be changed* when new content is pushed unless you want more drastic changes to overall layout of the webpage.

These are the folders that actually contain the content:

* `_pages`: the different pages on the webpage.
* `_posts`: *exclusively* the news articles shown on the landing page of the website.
* `assets`: multimedia (images, various files etc.) where you actually want the webpage to show/host.
  * `assets/images` subfolder: for storing the images. There is a further subfolder `people` within `images`, where we put the individual photos of group members
  * `assets/downloads` subfolder: for sharing data files etc. that you wish to be accessible to website visitors

## Update content online

All pages/posts are written in markdown format. [This](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) is a nice cheat-sheet on how to format text in markdown. **Please consult this for formatting.** 

To add pages/posts, use any one of the existing pages/posts as templates and modify. I advice copying from one of these pages/posts with the form of content that you want (e.g. if you want to create a new page/post with a photo inside, look for one existing page/post that has exactly this and use this as a template to modify).

Below I give examples on likely additions for your convenience, but perhaps the easiest is to pick a template resembling the content you want to create and modify. For things such as inserting hyperlinks and images, I often find the 'Preview' function here useful - it converts the plain text to something that resembles an HTML page (albeit without the styling) so at least you know you have successfully inserted a link or a placeholder for an image at the right places.

### Header
For all pages, at the top you will see a section (marked by the symbols `---`) where we specify the basic information of the page. For instance, if you are creating a new page, you would want to specify the title of the page etc. For each type of content (page/post) I will specify below what needs to be changed.

### Updating pages

The content is stored in `.md` files in `_pages` directory. Each main page of the website (accessible from menu bar at the top of the page) - i.e. 'People', 'Software' etc. - has its own `.md` file.

Please pay attention to the following 2 parameters within the header section at the top of the file:
* `title`: Obviously you know what to put. Just remember to update this in your new page/post.
* `permalink`: this determines how the link is configured, e.g. if you put `/people/someone-new`, then the eventual hyperlink for this page would be: 'https://fraternalilab.github.io/people/someone-new'

**IMPORTANT**: For **creating new personal profile**, after adding a new file with the personal profile, and then go to the `people.md` file and add this person to the list at the header. It is now in this form e.g.:
```
feature_row:
  - image_path: /assets/images/people/FF_glasses_2014-640x640.jpg
    title: "Franca Fraternali"
    url: /people/franca-fraternali
    excerpt: "Group Leader"
  - (another person)
...
```
Please make a copy of one chunk (four lines under one 'bullet point'), update the image path (this is the personal photo to be shown above their names), title, url, and their role (`excerpt`). These chunks are placed in the order as they appear on the landing page. The group photo is inserted below this chunk as a standard image (see below for formats).

#### Useful formatting tips
* Bold text: `**Bold text**` would look like **Bold text**.
* Italics: `*Italicized text*` would look like *Italicized text*.
* To insert a hyperlink within text: the syntax is: `I want a link to Google [here](https://google.com)` would look like: I want a link to Google [here](https://google.com).
* To insert an image within text: the syntax is: `![Alt. text for the image in case it cannot be shown](/assets/images/example.png)` (Note the addition of '!' at the front, that distinguishes this from inserting hyperlinks).

For reference you can always look for examples in any existing pages/posts that include an image / a download link.

### Updating posts

'Posts' refer to news updates (accessible from the bottom menu on the index page). All `.md` files in `_posts` directory.

**IMPORTANT**: you will see that all posts have filenames in this format: `2025-01-01-something.md`. **Please change the date as appropriate (year-month-day)** as the news will be shown in reverse chronological order (i.e. latest news come first) on the landing page. Now this is configured to 6 news posts at a time with a button to flick through news at the bottom of the panel.

Same formatting applies to the posts as in the pages. Compared to the pages you should see a different option in the header in this format:
```
header:
  teaser: /assets/images/something-about-the-news.png
```
This is for specifying the (eye-catching) image to be shown on the landing page about this news. The same image will be shown within the news article, *before* your text. Please upload the tailored image you have for this news article to `assets/images`, and update the filename here (note sometimes images are in `.jpg` format and sometimes `.png` so please change the file extension as well as appropriate.

## Updating content

This site was originally developed inside a docker container. All docker set up are available in the repo and follows this site: [here](https://www.cross-validated.com/Personal-website-with-Minimal-Mistakes-Jekyll-Theme-HOWTO-Part-I/).

*We used to have a Twitter feed on the left hand sidebar on the landing page, but since it becomes X it seems the plugin for this feed doesn't work anymore. So now we don't have it, we just have a link to Twitter/X.* 

Every time new content (even just uploading a new image!) is uploaded/pushed here, the website will be automatically recompiled. This has been set as an automatic workflow ('GitHub Action') that would trigger following an update, which will rewrite files in the `docs/`. This should take roughly 3-4 minutes to show up as you refresh the webpage on your browser for checks.

### Offline compilation (no longer needed since Nov 2025 but I just keep it here for reference)

To do so, follow [this link](https://www.cross-validated.com/Personal-website-with-Minimal-Mistakes-Jekyll-Theme-HOWTO-Part-III/). Briefly,

1. Build the website in production mode under the docker set up:

```
docker run --rm -it --volume="$PWD:/srv/jekyll" --volume="$PWD:/usr/src/app" --env JEKYLL_ENV=production jekyll/jekyll:3.8 jekyll build
```

This will update files in the `_site` directory.

2. Next, copy all files in the `_site` directory and paste into the `docs/` directory at the root of this repository.

3. The repository is set up in such a way that files in `docs/` are taken to build the html site. As soon as you update files in `docs/` the updates would show up as you refresh the website on your browser.
