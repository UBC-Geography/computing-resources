---
output-file: index.html
title: Cloud Computing
---

Similar to high performance computing (HPC), cloud computing provides hardware
for running resource-intensive computations, but while HPC focuses on completing
a complex set of tasks as quickly as possible with an extraordinarily powerful
set of resources, cloud computing has been traditionally dedicated to providing
hardware through virtual machines (VM) of varying specifications over a long
period of time in order to support ongoing services such as web applications and
databases.

## Digital Research Alliance (DRA)

Canada-based faculty and librarians with DRA accounts can create a VMs at any
time of the year by submitting a
[Rapid Access Service (RAS) request](https://docs.google.com/forms/d/e/1FAIpQLSeU_BoRk5cEz3AvVLf3e9yZJq-OvcFCQ-mg7p4AWXmUkd5rTw/viewform).
If the RAS resource limits noted below and in more detail
[here](https://docs.alliancecan.ca/wiki/Cloud_RAS_Allocations) are not
sufficient, additional resources can be requested through the annual Resource
Allocation Competition (RAC) with applications due between late September and
early November. Upon approval, RAC resources are granted the following April.

- [DRA - Cloud](https://docs.alliancecan.ca/wiki/Cloud)

The DRA Cloud provides access two different types of VMs with different use
cases in mind, which are listed below.

### Compute Instances

Compute VMs are ephemeral and provide a middle-ground between running batch jobs
on the DRA HPC clusters and Persistent VMs. They can provide a powerful solution
when using software that cannot be ran on the HPC clusters either natively or
via Apptainer or when running computations that can run for days and/or weeks.

For geography-related research and instruction, these instances can be
particularly useful for the following use cases:

- Spinning up a customized JupyterHub instance and/or RStudio server for a
  workshop or class
- Working with massive datasets in a desktop application, such as QGIS,
  AliceVision, or Blender, where access to a GPU can be significantly beneficial

#### RAS Resource Limits

- \# of VMs: 20
- vCPUs: 80
  - 16 per VM
- RAM: 300 GB
  - 180 GB per VM
- Storage: 10 TB
- vGPU: 16 GB of memory on an Nvidia V100

### Persistent Instances

These VMs are ideal for running continuous computations, like web crawlers, and
ongoing services, like web servers. It's important to remember that services
cannot be ran on the DRA Cloud indefinitely, so ensure you have a plan for your
VM's end-of-life (EOL) along with a set of clear security procedures before
creating it. The DRA requires that researchers reassess their cloud services
annually in April by submitting a form that restates the goals of the project
and necessary resources for continued use.

For geography-related research and instruction, these instances can be
particularly useful for the following use cases:

- Hosting a PostgreSQL database with PostGIS
- Running a web service with software like GeoServer, GeoNode, Ushahidi, uMap
  (OpenStreetMap), or QGIS server.
- Developing dynamic digital exhibits or publications with Omeka and/or Scalar.

Again, when working with persistent VMs, consider any implications that may come
from preserving your work once the VM is no longer available by asking yourself
whether your work can be easily exported, web archived, and/or hosted externally
with minimal resources and no long-term maintenance.

#### RAS Resource Limits

- \# of VMs: 10
- vCPUs: 25
  - 16 per VM
- RAM: 50 GB
  - 32 GB per VM
- Storage: 10 TB

## UBC IT

In some cases, the DRA Cloud may not be the best option for a research project.
In those cases, UBC IT can provide some budget-friendly alternatives. For
minimal LAMP-stack web applications, like WordPress, Drupal, or Omeka, UBC IT
provides simple shared hosting solutions, while more resource-intensive
applications and computation tasks can run on EduCloud VMs. Additionally, UBC IT
has begun a broker system that can enable resources to be requested from large
commercial cloud providers like Amazon, Microsoft, and Google with additional
support.

- [UBC IT - EduCloud Server Service](https://it.ubc.ca/services/web-servers-storage/educloud-server-service)

- [UBC IT - Hybrid Cloud Service](https://it.ubc.ca/services/web-servers-storage/hybrid-cloud-service)

## Commercial Cloud Computing Providers

Along with UBC IT's Hybrid Cloud Services, resources from commercial cloud
computing providers can be acquired with funding and credit opportunities via
UBC Advanced Research Computing (ARC). Prior to using a commercial cloud
computing provider, contact UBC ARC for consultation as they can provide
guidance in selecting the best provider for your project and identifying any
security concerns that may be applicable. This consultation can be crucial when
navigating the massive and overwhelming number of services/options presented by
commercial providers.

### Amazon Web Services (AWS)

To further support researchers in using allocated credits on AWS, UBC ARC
provides access to [RONIN](https://ronin.cloud/), a web application that can
simplify and increase the accessibility of clouding computing services.

- [UBC ARC RONIN](https://arc.ubc.ca/cloud-computing/arc-cloud-platform-ubc-arc-ronin)

- _[Geospatial Data Analytics on AWS](https://go.exlibris.link/g9MMmFL8)_

- [AWS - Geospatial ML with Amazon SageMaker](https://aws.amazon.com/sagemaker/geospatial/)

### Microsoft Azure

Azure integrates smoothly with Esri software, making it a strong option for
research that is heavily dependent on ArcGIS.

- [Azure Maps](https://azure.microsoft.com/en-us/products/azure-map)

- [Azure - Geospatial Data Processing and Analytics](https://learn.microsoft.com/en-us/azure/architecture/example-scenario/data/geospatial-data-processing-analytics-azure)

- [Azure - End-To-End Geospatial Storage, Analysis, and Visualization](https://learn.microsoft.com/en-us/azure/orbital/geospatial-reference-architecture)

### Google Cloud Platform (GCP)

- [Google Cloud - Geospatial Analytics](https://cloud.google.com/solutions/geospatial)
