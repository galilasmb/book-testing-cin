## Contents

- [Installation](#installation)
  - [Step 1: Installing Ruby](#step-1-installing-ruby)
  - [Step 2: Configuring Github Pages and running locally](#step-2-configuring-github-pages-and-running-locally)
  - [Step 3: Adding a new post](#step-3-adding-a-new-post)
  - [Step 4: Configuring menu and adding pages](#step-4-configuring-menu-and-adding-pages)
  - [Step 5: Adding an YouTube or Google Drive video](#step-5-adding-an-youtube-or-google-drive-video)
  - [Step 6 (Optional): Adding Jupyter Notebooks](#step-6-optional-adding-jupyter-notebooks)
- [Additional Information](#additional-information)

## Installation

Start forking this repository and after that follow these steps:

### Step 1: Installing Ruby

If you don't have Ruby installed, you can get it following these instructions: https://www.ruby-lang.org/en/documentation/installation/

It will be used to run this project locally in the next step.

### Step 2: Configuring Github Pages and running locally

After installing Ruby, go on your forked repository Github page, click on `Settings` tab and find a section called `Github pages` inside `Options`. Select a source (you can use **master**) and that's it, your repository is published. (You can find more information here: https://pages.github.com/)

Now, clone your forked repository and open it in a code editor (i.e. Visual Studio Code). Go to **\_config.yml** file and edit these lines:

```yaml
baseurl: "" # subpath for your site, e.g. /blog
url: "" # base hostname & protocol for your site, e.g. http://example.com
```

Change them to the subpath you'll use to publish the project. In this project we used: https://galilasmb.github.io/book-testing-cin, so these lines were modified to:

```yaml
baseurl: "/book-testing-cin"
url: "https://galilasmb.github.io"
```

You can also edit other options if you need.

Now, if you want to see how it looks like, you can run typing this in a console from root folder:

```
    bundle exec jekyll serve
```

After the project building, open your browser and type http://127.0.0.1:4000/[your base url] to see the result.

If you want to see theses changes published online, you must push them to repository and, after that, open your generated Github pages link (https://[your Github user].github.io/[you base url]).

### Step 3: Adding a new post

Creating a new post is very easy, just follow theses steps:

1. Create a new .md file in **\_post** path.
2. Add this configuration to **each new post**:

```xml

---
layout: post
title:  "Post Title"
date:   2020-07-01 19:48:36 -0300
image: 'https://www.csrhymes.com//img/static-site-generator.jpg'
categories: video
---

Insert your content here...

```

3. Change the post title
4. Insert the post date (This will influence the order in which it will appear on the website)
5. An image will appear in the posts sidebar, so choose an image or delete this line
6. Choose a post category (This will group posts in a specific tag)
7. Push your modifications

### Step 4: Configuring menu and adding pages

If you need to change the menu or add new pages, follow these instructions:

- Menu: https://github.com/chrisrhymes/bulma-clean-theme#menubar
- Pages: https://github.com/chrisrhymes/bulma-clean-theme#navigation

### Step 5: Adding an YouTube or Google Drive video

1. Create a .md file for a post
2. In your file, add a youtubeId and/or driveId key(s) (You can find these id values inside the video url like `dhh9zcA6Xwk` from https://www.youtube.com/watch?v=dhh9zcA6Xwk)

```xml
---
title: Page title
subtitle: Description
layout: page
show_sidebar: true
youtubeId: dhh9zcA6Xwk
driveId: dhh9zcA6Xwk
---

include youtubePlayer.html id=page.youtubeId
include googleDrivePlayer.html id=page.driveId

```

### Step 6 (Optional): Adding Jupyter Notebooks

When you need to add some python code to show examples, you can use [Binder](https://mybinder.org/).

For example, we generated a Binder from a HelloWorld.ipynb file in root folder:

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/galilasmb/book-testing-cin/master?filepath=HelloWorld.ipynb)

## Additional information

### References

In this project we are using some frameworks and tools, these are some references that we consider important to have a full understanding of it:

- Jekyll: https://github.com/jekyll/jekyll
- Bulma Clean Theme: https://github.com/chrisrhymes/bulma-clean-theme
- Binder: https://mybinder.org/
- Creating your blog for free using Jekyll + Github pages tutorial: https://medium.com/20percentwork/creating-your-blog-for-free-using-jekyll-github-pages-dba37272730a

**Enjoy :D**
