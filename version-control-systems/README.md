---
output-file: index.html
title: Version Control Systems
---

Implementing version control is a commonly used best practice among programmers,
and its usage is strongly encouraged for researchers whether they are working
with large codebases or small Jupyter Notebooks. Version control is especially
helpful when collaborating with other researchers or developers as it enables
changes to be tracked coherently and new code to be explored separately from a
stable, main codebase in easily managed branches.

- [The Turing Way - Version Control](https://the-turing-way.netlify.app/reproducible-research/vcs)

## Code

### [Git](https://git-scm.com/)

Git is by far the most popular version control system and comes with a powerful
command line interface while integrating with code sharing and development
platforms, like GitHub and GitLab.

- [UBC Library Research Commons - Introduction to Git and GitHub](https://ubc-library-rc.github.io/intro-git/)

- [Digital Research Alliance - Git Tutorial and Workshops](https://mint.westdri.ca/git/)

- _[Pro Git](https://git-scm.com/book/en/v2)_

### GitHub

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

While GitHub excels at displaying code on the web, it also supports some other
interesting functionalities relevant to geospatial computing. For example, if
you don't mind storing your tabular data in CSV or GeoCSV, GitHub will render
the data to an interactive table, which can be easily searched and edited.

- [GitHub Documentation - Rendering CSV and TSV Data](https://docs.github.com/en/repositories/working-with-files/using-files/working-with-non-code-files#rendering-csv-and-tsv-data)

You can also quickly generate basic web maps directly within your repository by
storing your vector data in the GeoJSON or TopoJSON format. GitHub will render
the vector data with Azure Maps and Leaflet.js. The generated web map can then
be embedded on different sites with a simple snippet of JavaScript.

- [GitHub Documentation - Mapping GeoJSON/TopoJSON files on GitHub](https://docs.github.com/en/repositories/working-with-files/using-files/working-with-non-code-files#mapping-geojsontopojson-files-on-github)

- [GitHub GeoJSON Web Map Example](https://viewscreen.githubusercontent.com/view/geojson?url=https%3a%2f%2fraw.githubusercontent.com%2fbenbalter%2fdc-wifi-social%2fmaster%2fbars.geojson)

### Integrations

#### JupyterLab

- [How to Use the JupyterLab Git Extension](https://blog.reviewnb.com/jupyterlab-git-extension/)

- [JupyterLab-Git README](https://github.com/jupyterlab/jupyterlab-git#jupyterlab-git)

- [Working with Private GitHub Repositories from JupyterHub](https://ubc-geography.github.io/computing-resources/version-control-systems/jupyterhub-private-repo.html)

#### RStudio

- [GitHub and RStudio](https://resources.github.com/github-and-rstudio)

- _[Happy Git and GitHub for the UseR](https://happygitwithr.com/usage-intro.html)_

#### VS Code

- [VS Code Extensions - Remote Repositories](https://marketplace.visualstudio.com/items?itemName=github.remotehub)

## Data

While version control systems are most commonly applied to code, to further
ensure the reproducibility of their work, researchers have been developing and
improving systems that can work fluently with their data as well. These systems
are often built to work atop or adjacent to Git while adding functionality to
manage and store large datasets via [Git LFS](https://git-lfs.com/) or
[object storage](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html).

- [The Turing Way - Version Control for Data](https://the-turing-way.netlify.app/reproducible-research/vcs/vcs-data)

### [Kart](https://kartproject.org/)

Kart is a tool that has been built on top of Git and extends its functionality
to work with vector datasets while also integrating with Git LFS (Large File
Storage) to handle large raster datasets. The Kart developers also provide a
QGIS plugin to ensure easy integration.

- [Kart Documentation](https://docs.kartproject.org/en/latest/index.html)

- [Kart QGIS Plugin](https://plugins.qgis.org/plugins/kart/)

### [DataLad](https://www.datalad.org/)

Datalad provides a general-purpose data version control system that supports a
broad set of storage options including Microsoft OneDrive, DRA's Arbutus object
storage (OpenStack Swift), and a range of other S3-compatible object storage
providers.

- _[Datalad: The Handbook](https://handbook.datalad.org/en/latest/index.html)_

### [DVC](https://dvc.org/)

While applicable to a range of other data-intensive tasks, DVC is a data version
control system that specializes in machine learning. It supports fewer storage
options compared to Datalad, but can provide a smoother integration and setup
experience in certain applications.

- [DVC Documentation](https://dvc.org/doc)

- [WestDRI - Version Control for Data Science and Machine Learning with DVC](https://youtu.be/2MQVF78FRKs?si=b2UnIRcPPTMQSL7K)
