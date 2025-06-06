---
output-file: index.html
title: Version Control Systems
# change to date to last-modified after next modification
date: 2025-01-16
---

Implementing version control is a commonly used best practice among programmers,
and its usage is strongly encouraged for researchers whether they are working
with large codebases or small Jupyter Notebooks. Version control is especially
helpful when collaborating with other researchers or developers as it enables
changes to be tracked coherently and new code to be explored separately from a
stable, main codebase.

- [Opensource Computing for Earth Science Education (OCESE) Project - Introduction to Version Control and Git](https://eoas-ubc.github.io/tut-git-intro.html){target="\_blank"}

- [The Turing Way - Version Control](https://the-turing-way.netlify.app/reproducible-research/vcs){target="\_blank"}

## Code

### Git

Git is by far the most popular version control system and comes with a powerful
command line interface while integrating with code sharing and development
platforms, like GitHub and GitLab.

UBC Library Research Commons frequently runs introductory workshops on Git and
GitHub, which are listed
[here](https://libcal.library.ubc.ca/calendar/?t=g&q=git){target="\_blank"}. And
the materials for these workshops are available below:

- [UBC Library Research Commons - Introduction to Git and GitHub](https://ubc-library-rc.github.io/intro-git/){target="\_blank"}

Additionally, the SFU's Research Computing Group provides a full-day workshop on
Bash during their annual Summer School in early June with some of the materials
for that course available below:

- [Digital Research Alliance - Git Tutorial and Workshops](https://mint.westdri.ca/git/){target="\_blank"}

Additional Resources:

- [Software Carpentry - Version Control with Git](https://swcarpentry.github.io/git-novice/){target="\_blank"}

- _[Pro Git](https://git-scm.com/book/en/v2){target="\_blank"}_

- _Beginning Git and GitHub: Version Control, Project Management and Teamwork
  for the New Developer_ :
  [UBC Library](https://go.exlibris.link/G3VfpGll){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1427243462){target="\_blank"}

- _Mastering Git_ :
  [UBC Library](https://go.exlibris.link/zJxLHm6W){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1454574509){target="\_blank"}

### GitHub

GitHub is a popular platform for sharing source code and Jupyter Notebooks as
Git repositories. These can either be public and shared broadly with other users
to copy (clone) or private for restricted sharing among invited users. UBC LT
provides access to GitHub Enterprise which can securely share repositories among
students within a single course or with other UBC collaborators.

- [GitHub Documentation](https://docs.github.com/en){target="\_blank"}

- _GitHub for Next-Generation Coders_ :
  [UBC Library](https://go.exlibris.link/CLVkVZyK){target="\_blank"} |
  [WorldCat](https://search.worldcat.org/title/1446794123){target="\_blank"}

- [UBC LT - GitHub Instructor Guide](https://lthub.ubc.ca/guides/github-instructor-guide/){target="\_blank"}

GitHub Desktop provides a helpful graphical user interface that can help in
managing local Git repositories and pushing changes to remote repositories on
GitHub.

- [GitHub Desktop Documentation](https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/overview/getting-started-with-github-desktop){target="\_blank"}

An additional benefit to storing your code in a public repository on GitHub is
that your code can easily be archived into
[Zenodo](https://about.zenodo.org/){target="\_blank"}, where it will receive a
digital object identifier (DOI). This then makes it extraordinarily easy for
your code to be cited and accessed by other researchers. If later you make
revisions or improvements to your code, you can cut a new release and Zenodo
will automatically update your archive and assign a new DOI.

- [GitHub Documentation - Referencing and Citing Content](https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content){target="\_blank"}

While GitHub excels at displaying code on the web, it also supports some other
interesting functionalities relevant to geospatial computing. For example, if
you don't mind storing your tabular data in CSV or GeoCSV, GitHub will render
the data to an interactive table, which can be easily searched and edited.

- [GitHub Documentation - Rendering CSV and TSV Data](https://docs.github.com/en/repositories/working-with-files/using-files/working-with-non-code-files#rendering-csv-and-tsv-data){target="\_blank"}

You can also quickly generate basic web maps directly within your repository by
storing your vector data in the GeoJSON or TopoJSON format. GitHub will render
the vector data with Azure Maps and Leaflet.js. The generated web map can then
be embedded on different sites with a simple snippet of JavaScript.

- [GitHub Documentation - Mapping GeoJSON/TopoJSON files on GitHub](https://docs.github.com/en/repositories/working-with-files/using-files/working-with-non-code-files#mapping-geojsontopojson-files-on-github){target="\_blank"}

- [GitHub GeoJSON Web Map Example](https://viewscreen.githubusercontent.com/view/geojson?url=https%3a%2f%2fraw.githubusercontent.com%2fbenbalter%2fdc-wifi-social%2fmaster%2fbars.geojson){target="\_blank"}

### Integrations

#### JupyterLab

- [How to Use the JupyterLab Git Extension](https://blog.reviewnb.com/jupyterlab-git-extension/){target="\_blank"}

- [JupyterLab-Git README](https://github.com/jupyterlab/jupyterlab-git#jupyterlab-git){target="\_blank"}

- [Working with Private GitHub Repositories from JupyterHub](https://ubc-geography.github.io/computing-resources/version-control-systems/jupyterhub-private-repo.html){target="\_blank"}

#### RStudio

- [GitHub and RStudio](https://resources.github.com/github-and-rstudio){target="\_blank"}

- _[Happy Git and GitHub for the UseR](https://happygitwithr.com/usage-intro.html){target="\_blank"}_

#### VS Code

- [VS Code Extensions - Remote Repositories](https://marketplace.visualstudio.com/items?itemName=github.remotehub){target="\_blank"}

## Data

While version control systems are most commonly applied to code, to further
ensure the reproducibility of their work, researchers have been developing and
improving systems that can work fluently with their data as well. These systems
are often built to work atop or adjacent to Git while adding functionality to
manage and store large datasets via
[Git LFS](https://git-lfs.com/){target="\_blank"} or
[object storage](https://ubc-geography.github.io/computing-resources/cloud-computing/object-storage.html){target="\_blank"}.

- [The Turing Way - Version Control for Data](https://the-turing-way.netlify.app/reproducible-research/vcs/vcs-data){target="\_blank"}

### [Kart](https://kartproject.org/){target="\_blank"}

Kart is a tool that has been built on top of Git and extends its functionality
to work with vector datasets while also integrating with Git LFS (Large File
Storage) to handle large raster datasets. The Kart developers also provide a
QGIS plugin to ensure easy integration.

- [Kart Documentation](https://docs.kartproject.org/en/latest/index.html){target="\_blank"}

- [Kart QGIS Plugin](https://plugins.qgis.org/plugins/kart/){target="\_blank"}

### [DataLad](https://www.datalad.org/){target="\_blank"}

DataLad provides a general-purpose data version control system that supports a
broad set of storage options including Microsoft OneDrive, DRA's Arbutus object
storage (OpenStack Swift), and a range of other S3-compatible object storage
providers.

- _[Datalad: The Handbook](https://handbook.datalad.org/en/latest/index.html){target="\_blank"}_

- [WestDRI - Distributed File Storage with git-annex](https://training.westdri.ca/tools/rdm/#distributed-file-storage-with-git-annex){target="\_blank"}

- [WestDRI - Data Management with DataLad](https://training.westdri.ca/tools/rdm/#data-management-with-datalad){target="\_blank"}

- [WestDRI - Distributed Datasets with Datalad](https://training.westdri.ca/tools/rdm/#distributed-datasets-with-datalad){target="\_blank"}

### [DVC](https://dvc.org/){target="\_blank"}

While applicable to a range of other data-intensive tasks, DVC is a data version
control system that specializes in machine learning. It supports fewer storage
options compared to Datalad, but can provide a smoother integration and setup
experience in certain applications.

- [DVC Documentation](https://dvc.org/doc){target="\_blank"}

- [WestDRI - Version Control for Data Science and Machine Learning with DVC](https://youtu.be/2MQVF78FRKs?si=b2UnIRcPPTMQSL7K){target="\_blank"}
