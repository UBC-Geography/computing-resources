---
output-file: index.html
title: Digital Communications
date: last-modified
---

## WordPress

An open-source content management system that is used to host a wide range of
websites and web applications.

### UBC Blogs

[UBC Blogs](https://blogs.ubc.ca/){target="\_blank"} is built on top of
WordPress. UBC provides a large collection of documentation to help faculty and
students get started with using it as a tool for scholarly communications.

- [UBC Blogs Video Tutorials](https://wiki.ubc.ca/UBC_Blogs_Screencasts){target="\_blank"}

- [UBC Blogs Instructor Guide](https://lthub.ubc.ca/guides/ubc-blogs-instructor-guide/){target="\_blank"}

- [UBC Blogs FAQ](https://blogs.ubc.ca/faq/){target="\_blank"}

- [WordPress Clinics at UBC CTLT](https://events.ctlt.ubc.ca/?s=wordpress){target="\_blank"}

### Additional Resources

Having just a basic familiarity with WordPress' user interface, is often enough
to meet the needs of most use cases. The following resources can provide
more-in-depth walkthroughs of WordPress' for leveraging its more advanced
functionalities.

- [WordPress Documentation](https://wordpress.org/documentation/){target="\_blank"}

- WordPress 101 -- Video Course :
  [UBC Library](https://go.exlibris.link/7mDvM1rZ){target="\_blank"}

- _WordPress: The Missing Manual_ :
  [UBC Library](https://go.exlibris.link/qfbFTbLz){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1152988879){target="\_blank"}

- _WordPress All-in-One for Dummies_ :
  [UBC Library](https://go.exlibris.link/CH9cfmW0){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1420169498){target="\_blank"}

- _WordPress Styling with Blocks, Patterns, Templates, and Themes_ :
  [UBC Library](https://go.exlibris.link/D34NjqgH){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1424750704){target="\_blank"}

### Alternative Hosting Options

[Note on UBC CMS](https://cms.ubc.ca/){target="\_blank"}

- [UBC IT Shared Hosting](https://it.ubc.ca/services/web-servers-storage/shared-web-hosting){target="\_blank"}

- [Digital Research Alliance - Cloud - Persistent Instances (VMs)](https://ubc-geography.github.io/computing-resources/cloud-computing/#persistent-instances){target="\_blank"}

- [Reclaim Hosting - Reclaim Press](https://reclaim.press/){target="\_blank"}

## Static Site Generators (SSG) / Web Publishing

As alternatives to WordPress, static site generators give up easy-to-use
interfaces via a content management system and a range of other functionalities
to create faster, more reliable, and more secure websites, where content is
managed via a set of Markdown files. Additionally, these tools often have
smaller sets of themes that users can install to customize the styling of their
website, thus requiring a better understanding of HTML, CSS, and JavaScript to
develop a more customized look and feel to a website.

Statically generated sites can be hosted nearly anywhere on the web, including:

- [Digital Research Alliance - Cloud / Arbutus Object Storage](https://docs.alliancecan.ca/wiki/Arbutus_object_storage){target="\_blank"}

- [GitHub Pages](https://docs.github.com/en/pages){target="\_blank"} - 1 GB
  Limit

### Quarto

Developed by the same company working on RStudio, Quarto provides a powerful
tool for publishing scientific and technical work in a range of formats and acts
as a successor to R Markdown. Code in Python, R, Julia, and JavaScript can all
be represented and rendered along with Pandoc-style Markdown. Interactive
visualizations can also be embedded on supported formats using R Shiny,
Observable JS, or Jupyter Widgets.

::: {.callout-note}

If rendering and exporting HTML files in RStudio using Quarto, ensure you also
export the quarto_files directory, which holds necessary CSS and JavaScript
files.

:::

- [Quarto Webinars](https://mint.westdri.ca/tools/wb_quarto.html){target="\_blank"}

- [Quarto Documentation](https://quarto.org/docs/guide/){target="\_blank"}

### R Markdown (R)

R Markdown provides an authoring framework that enables code to be rendered
alongside Markdown and published in multiple formats. See Quarto for a successor
to R Markdown.

::: {.callout-note}

HTML files rendered via R Markdown use inline scripts and CSS, which can create
sometimes unnecessarily large files, but they ensure that the file displays
consistently without external files.

:::

- [R Markdown Documentation](https://rmarkdown.rstudio.com/lesson-1.html){target="\_blank"}

### Jekyll (Ruby)

One of the most widely used static site generators. This SSG integrates smoothly
with GitHub Pages to quickly render websites directly from a GitHub repository.
Due to its wide adoption, it also includes a wide range of open-source themes
that can be used to customize the style of a website.

- [UBC Library Research Commons - Introduction to Jekyll](https://ubc-library-rc.github.io/intro-jekyll){target="\_blank"}

- [UBC Library Research Commons - Intermediate Jekyll](https://ubc-library-rc.github.io/intermediate-Jekyll/){target="\_blank"}

- [UBC Library Research Commons - Building a project website with Jekyll and GitHub Pages](https://ubc-library-rc.github.io/intro-project-sites/){target="\_blank"}

### Quire (JavaScript)

Developed and maintained by [Getty](https://www.getty.edu/), Quire is built on
the static site generator, [11ty](https://www.11ty.dev/), and focuses on acting
as a tool that can facilitate the creation of media-rich, sustainable, and
easily preserved digital publications.

- [Quire Overview, Documentation, and Resources](https://quire.getty.edu/)

- [Quire - GitHub README](https://github.com/thegetty/quire)

## Digital Exhibit Tools

Storing and presenting digital assets, like images, audio, and video files, can
be easily managed via content management systems and static site generators that
specialize in digital exhibits.

- [UBC Library Research Commons - Survey of Digital Exhibit Tools](https://ubc-library-rc.github.io/digital-exhibits-survey/){target="\_blank"}

### Omeka Classic & Omeka-S

Omeka Classic is targeted towards small, individually developed projects, while
Omeka-S focuses on developing larger scale, institutional-wide repositories with
multiple collections or projects. Both are considered web applications as they
include content management systems that provide an easy-to-use interface for
developing and managing digital exhibits.

- [UBC Library Research Commons - Building Digital Exhibits with Omeka](https://ubc-library-rc.github.io/intro-omeka/){target="\_blank"}

- [Omeka: A User's Guide: Introduction](https://guides.library.illinois.edu/omeka/intro){target="\_blank"}

#### Cloud Hosting

- [Deploying Omeka Classic on the Alliance Cloud](https://ubc-geography.github.io/computing-resources/cloud-computing/deploying-omeka-classic.html){target="\_blank"}

- [UBC IT Shared Hosting](https://it.ubc.ca/services/web-servers-storage/shared-web-hosting){target="\_blank"}

- [Omeka Classic Documentation](https://omeka.org/classic/docs/){target="\_blank"}

- [Omeka-S Documentation](https://omeka.org/s/docs/user-manual/){target="\_blank"}

### CollectionBuilder

Lacking a content management system, CollectionBuilder centers the development
and management of digital exhibits around CSVs, which can be easily created and
managed via a spreadsheet editor. Built as a theme around a static site
generator (Jekyll), CollectionBuilder creates digital exhibits as
easy-to-preserve websites.

- [CollectionBuilder Documentation](https://collectionbuilder.github.io/cb-docs/){target="\_blank"}

- [CollectionBuilder Example - Idaho Queered](https://www.lib.uidaho.edu/queered/){target="\_blank"}
