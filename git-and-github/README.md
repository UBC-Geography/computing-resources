---
output-file: index.html
---

# Git & GitHub

Implementing version control is a commonly used best practice among programmers,
and its usage is strongly encouraged for researchers whether they are working
with large codebases or small Jupyter Notebooks. Version control is especially
helpful when collaborating with other researchers or developers as it enables
changes to be tracked coherently and new code to be explored separately from a
stable, main codebase in easily managed branches.

- [UBC Library Research Commons - Introduction to Git and GitHub](https://ubc-library-rc.github.io/intro-git/)

## [Git](https://git-scm.com/)

Git is by far the most popular version control system and comes with a powerful
command line interface while integrating with code sharing and development
platforms, like GitHub and GitLab.

- [Digital Research Alliance - Git Tutorial and Workshops](https://mint.westdri.ca/git/)

- _[Pro Git](https://git-scm.com/book/en/v2)_

## GitHub

GitHub is a popular platform for sharing source code and Jupyter Notebooks as
Git repositories. These can either be public and shared broadly with other users
to copy (clone) or private for restricted sharing among invited users. UBC LT
provides access to GitHub Enterprise which can securely share repositories among
students within a single course or with other UBC collaborators.

- [GitHub Documentation](https://docs.github.com/en)

- [UBC LT - GitHub Instructor Guide](https://lthub.ubc.ca/guides/github-instructor-guide/)

GitHub Desktop provides a helpful graphical user interface that can help in
managing local Git repositories and pushing changes to remote repositories on
GitHub.

- [GitHub Desktop Documentation](https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/overview/getting-started-with-github-desktop)

An additional benefit to storing your code in a public repository on GitHub is
that your code can easily be archived into [Zenodo](https://about.zenodo.org/),
where it will receive a digital object identifier (DOI). This then makes it
extraordinarily easy for your code to be cited and accessed by other
researchers. If later you make revisions or improvements to your code, you can
cut a new release and Zenodo will automatically update your archive and assign a
new DOI.

- [GitHub Documentation - Referencing and Citing Content](https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content)

## Integrations

### JupyterLab

- [How to Use the JupyterLab Git Extension](https://blog.reviewnb.com/jupyterlab-git-extension/)

- [JupyterLab-Git README](https://github.com/jupyterlab/jupyterlab-git#jupyterlab-git)

### RStudio

- [GitHub and RStudio](https://resources.github.com/github-and-rstudio)

- _[Happy Git and GitHub for the UseR](https://happygitwithr.com/usage-intro.html)_

### VS Code

- [VS Code Extensions - Remote Repositories](https://marketplace.visualstudio.com/items?itemName=github.remotehub)

## [Kart](https://kartproject.org/)

Kart is a tool that has been built on top of Git and extends its functionality
to work with vector datasets while also integrating with Git LFS (Large File
Storage) to handle large raster datasets. The Kart developers also provide a
QGIS plugin to ensure easy integration.

- [Kart Documentation](https://docs.kartproject.org/en/latest/index.html)

- [Kart QGIS Plugin](https://plugins.qgis.org/plugins/kart/)
