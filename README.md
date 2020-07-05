## Contents

- [Installation](#installation)
  - [Step 1: Installing Ruby](#step-1-installing-ruby)
  - [Step 2: Configuring Github Pages and running locally](#step-2-configuring-github-pages-and-running-locally)
  - [Step 3: Adding a new post](#step-3-adding-a-new-post)
  - [Step 4: Configuring menu and adding pages](#step-4-configuring-menu-and-adding-pages)
  - [Step 5: Adding a YouTube or Google Drive video](#step-5-adding-a-youtube-or-google-drive-video)
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

After the project building, open your browser and type http://127.0.0.1:4000/ [your base url] to see the result.

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
image: 'https://www.csrhymes.com/img/static-site-generator.jpg'
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

#### Menubar

(Adapted from: https://github.com/chrisrhymes/bulma-clean-theme#menubar)

The menubar gets its content from a data file in site's `_data` directory. Simply set the name of your data file in the page's menubar setting in the frontmatter like this:

```yaml
show_sidebar: false
menubar: example_menu
```

You will probably want to disable the show_sidebar otherwise there will be little room for the page content. 

##### Changing the menubar data file

Change the data file in _data directory and use the following format:

```yaml
- label: Example Menu
  items:
    - name: Home
      link: /
    - name: Pages
      link: /#
      items:
      - name: Página 1
        link: /page-1/
      - name: Página 2
        link: /page-2/
      - name: Página 3
        link: /page-3/
    - name: Sobre
      link: /about/
```

##### Multiple menus

You may make multiple menus in the same file, separated by the label

```yaml
- label: Menu Label
  items:
    - name: Example item
      link: /example-item/
- label: Second Menu Label
  items:
    - name: Parent Item
      link: /parent-item/
      items:
        - name: Sublink 
          link: /sublink/
        - name: Sublink 2
          link: /sublink2/
- label: Third Menu Label
  items:
    - name: Another example item
      link: /another-example-item/
```

#### Navigation

(Adapted from: https://github.com/chrisrhymes/bulma-clean-theme#navigation)

For the top navigation, change the navigation.yml file in `_data` directory with the following format with the pages you want to include in the top navigation. You can also add items to a dropdown menu.

```yaml
- name: Páginas
  link: /#
  dropdown:
    - name: Página 1
      link: /page-1/
    - name: Página 2
      link: /page-2/
    - name: Página 3
      link: /page-3/

- name: Material
  link: /material/
- name: Notebook
  link: https://mybinder.org/v2/gh/galilasmb/book-testing-cin/master?filepath=HelloWorld.ipynb
- name: Sobre
  link: /about/
```

### Step 5: Adding a YouTube video, Google Drive video or Google Forms

1. Create a .md file for a post or page
2. In your file configuration, add a youtubeId and/or driveId and/or formsId key(s)

```xml
---
title: Page title
subtitle: Description
layout: page
show_sidebar: true
youtubeId: dhh9zcA6Xwk
driveId: dhh9zcA6Xwk
formsId: 1uYK_9QJaZN8a6eDGco0cMzMzEgReFM7JqI2h6EeEitU
---

Insert the commands here...

```

2.1 Youtube Video:
You can find this id value inside the video url like `dhh9zcA6Xwk` from https://www.youtube.com/watch?v=dhh9zcA6Xwk

```xml
{% include youtubePlayer.html id=page.youtubeId %}
```

2.2. Google Drive
Click on the video and on share link, check the option: Anyone with the link can view, and copy your id inside url like `1XejOcnSVg5KWxweoe-TXaDol-dqTeHTE` from https://drive.google.com/file/d/1XejOcnSVg5KWxweoe-TXaDol-dqTeHTE/view?usp=sharing. Make sure the video is shared as public.

```xml
{% include googleDrivePlayer.html id=page.driveId %}
```

2.3. Google Forms
After creating the form, click in send, in link icon and copy it, you can find the id inside url like `1FAIpQLScPE3QyL3DsoXuOgY-uaVBEMQjZ1Seuckubarbi1JTIRygtWw` from https://docs.google.com/forms/d/e/1FAIpQLScPE3QyL3DsoXuOgY-uaVBEMQjZ1Seuckubarbi1JTIRygtWw/viewform?usp=sf_link
```xml
{% include forms.html id=page.formsId %}
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
