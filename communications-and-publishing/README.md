# Communications and Publishing

## WordPress

Open-source content management system software that is used to host a
wide range of websites and web applications. Both UBC Blogs and UBC CMS
are built on top of this software, so UBC provides a large collection of
documentation to help faculty and students in getting started with using
it. The wide adoption of this software also means there is plenty of
documentation for self-hosting a WordPress server, but strong caution
should be taken as security vulnerabilities are frequently identified
and taken advantage of by bad actors.

- [UBC Arts ISIT Video Tutorials](https://isit.web.arts.ubc.ca/video-tutorial-introduction-to-ubc-cms/)

- [IThemes Tutorials](https://ithemes.com/tutorials/)

- [UBC Arts ISIT WordPress Resources](https://isit.arts.ubc.ca/resources/)

- [WordPress Clinics at UBC CTLT](https://events.ctlt.ubc.ca/?s=wordpress)

### UBC Blogs

- [UBC Blogs vs. UBC CMS](https://support.cms.ubc.ca/cms-manual/getting-started/differences-between-ubc-cms-and-ubc-blogs/)

- [UBC Blogs FAQ](https://blogs.ubc.ca/faq/)

- [UBC Blogs Video Tutorials](https://wiki.ubc.ca/UBC_Blogs_Screencasts)

- [UBC Blogs Instructor Guide](https://lthub.ubc.ca/guides/ubc-blogs-instructor-guide/)

### UBC CMS

- [UBC CMS Manual](https://support.cms.ubc.ca/cms-manual/)

### Cloud Hosting

- [UBC IT Shared Hosting](https://it.ubc.ca/services/web-servers-storage/shared-web-hosting)

- [WordPress Documentation](https://wordpress.org/documentation/)

- [WordPress 101 -- Video Course](https://learning.oreilly.com/videos/wordpress-101/9781800566415/?sso_link=yes&sso_link_from=univ-british-columbia)

- [WordPress: The Missing Manual](http://resolve.library.ubc.ca/cgi-bin/catsearch?bid=11890511)

## Static Site Generators (SSG) / Web Publishing

As alternatives to WordPress, static site generators give up easy-to-use
interfaces via a content management system and a range of other
functionalities to create faster, more reliable, and more secure
websites, where content is managed via a set of Markdown files.
Additionally, these tools often have smaller sets of themes that users
can install to customize the styling of their website, thus requiring a
better understanding of HTML, CSS, and JavaScript to develop a more
customized look and feel to a website.

### Quarto

Developed by the same company working on RStudio, Quarto provides a
powerful tool for publishing scientific and technical work in a range of
formats and acts as a successor to R Markdown. Code in Python, R, Julia,
and JavaScript can all be represented and rendered along with
Pandoc-style Markdown. Interactive visualizations can also be embedded
on supported formats using R Shiny, Observable JS, or Jupyter Widgets.
Note: If rendering and exporting HTML files in RStudio using Quarto,
ensure you also export the quarto_files directory, which holds necessary
CSS and JavaScript files.

- [Quarto Webinars](https://mint.westdri.ca/tools/quarto_webinar.html)

- [Quarto Documentation](https://quarto.org/docs/guide/)

### R Markdown (R)

Developed by the company behind RStudio, R Markdown provides an
authoring framework that enables code to be rendered alongside Markdown
and published in multiple formats. See Quarto for a successor to R
Markdown. Note: HTML files rendered via R Markdown use inline scripts
and CSS, which can create sometimes unnecessarily large files, but they
ensure that the file displays consistently without external files.

- [R Markdown Documentation](https://rmarkdown.rstudio.com/lesson-1.html)

### Jekyll (Ruby)

One of the most used static site generators. This SSG integrates
smoothly with GitHub Pages to quickly render websites directly from a
GitHub repository. Due to its wide adoption, it also includes a wide
range of open-source themes that can be used to customize the style of a
website.

- [UBC Library Research Commons - Introduction to Jekyll](https://ubc-library-rc.github.io/intro-jekyll)

- [UBC Library Research Commons - Intermediate Jekyll](https://ubc-library-rc.github.io/intermediate-Jekyll/)

- [UBC Library Research Commons - Building a project website with Jekyll and GitHub Pages](https://ubc-library-rc.github.io/intro-project-sites/)

- [Jekyll Documentation](https://jekyllrb.com/docs/)

## Digital Exhibit Tools

Storing and presenting digital assets, like images, audio, and video
files, can be easily managed via content management systems and static
site generators that specialize in digital exhibits.

- [UBC Library Research Commons - Survey of Digital Exhibit Tools](https://ubc-library-rc.github.io/digital-exhibits-survey/)

### Omeka Classic & Omeka-S

Omeka Classic is targeted towards small, individually developed
projects, while Omeka-S focuses on developing larger scale,
institutional-wide repositories with multiple collections or projects.
Both are considered web applications as they include content management
systems that provide an easy-to-use interface for developing and
managing digital exhibits.

- [UBC Library Research Commons - Building Digital Exhibits with Omeka](https://github.com/ubc-library-rc/intro-omeka)

- [Omeka: A User's Guide: Introduction](https://guides.library.illinois.edu/omeka/intro)

#### Cloud Hosting

- [UBC IT Shared Hosting](https://it.ubc.ca/services/web-servers-storage/shared-web-hosting)

- [Omeka Classic Documentation](https://omeka.org/classic/docs/)

- [Omeka-S Documentation](https://omeka.org/s/docs/user-manual/)

### CollectionBuilder

Lacking a content management system, CollectionBuilder centers the
development and management of digital exhibits around CSVs and Markdown.
Built as a theme around a static site generator (Jekyll),
CollectionBuilder creates digital exhibits as fast and easy-to-preserve
websites.

- [CollectionBuilder Documentation](https://collectionbuilder.github.io/cb-docs/)
