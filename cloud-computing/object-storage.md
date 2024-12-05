---
title: Object Storage
---

Object storage, also known as blob storage or even S3 storage in the context of
cloud computing as it has become synonymous with Amazon's Simple Storage Service
(S3), can provide a cheap and easy-to-implement solution for storing and sharing
files of widely varying sizes.

Cloud-based object storage can fluently handle file uploads when working with
extraordinarily large files while reducing opportunities for data loss by
providing an extremely high level of redundancy and durability. Once files are
stored in an object storage bucket/container, they can be made publicly
available without needing to setup and configure a web server.

Common use cases include:

- Storing and serving geospatial datasets, particularly those that are
  [cloud-optimized](https://guide.cloudnativegeo.org/){target="\_blank"}

- Backing up and/or storing archival data

- Storing and hosting media assets (images, audio, video, etc.)

- Hosting static websites

## S3-Compatible Clients

Most cloud-based object storage providers support Amazon's S3 API meaning that
they can be accessed and managed via an S3-compatible client. If you are using
multiple cloud storage providers, these are helpful tool to get familiar with.

- [Cyberduck](https://cyberduck.io/){target="\_blank"}

- [Rclone](https://rclone.org/){target="\_blank"}

## UBC ARC Chinook

UBC faculty members can access object storage via UBC ARC's Chinook platform.
Overall storage capacity is determined by allocation awards while individual
files stored on the platform can be up to 5 TB. While Globus remains the
recommended tool for managing object storage on Chinook, an S3 API can be
enabled upon request thus giving you the ability to use the noted S3 clients
above.

For more details about Chinook, see:
[Research Data Storage](https://ubc-geography.github.io/computing-resources/research-data-management/research-data-storage.html#ubc-chinook){target="\_blank"}

## Digital Research Alliance (DRA)

Faculty across Canada can also access up to 10 TB of object storage via DRA
Cloud's Arbutus data centre (University of Victoria) by submitting a
[Rapid Access Service (RAS) request](https://docs.google.com/forms/d/e/1FAIpQLSeU_BoRk5cEz3AvVLf3e9yZJq-OvcFCQ-mg7p4AWXmUkd5rTw/viewform){target="\_blank"}.
If those limits are not sufficient, additional resources can be requested
through the annual Resource Allocation Competition (RAC) with applications due
between late September and early November. Upon approval, RAC resources are
granted the following April.

- [DRA - Arbutus Object Storage](https://docs.alliancecan.ca/wiki/Arbutus_object_storage){target="\_blank"}

Projects allocated on the Arbutus cloud are administered through an OpenStack
dashboard, which provides limited functionality for managing object storage. If
you need more flexibility, you'll want to install one of the S3-compatible
clients listed above or alternatively an OpenStack Swift
[connector](https://cyberduck.io/openstack/){target="\_blank"} or client.

### [OpenStack Swift Client](https://docs.openstack.org/python-swiftclient/latest/cli/index.html)

OpenStack provides an official client for Swift services that can be installed
and ran via Python. This tool is not recommended for Windows environments as it
should be ran from a Bash shell.

```bash
# Install the openstack-swift CLI tool via Python
python -m pip install openstack-swift
# Download OpenStack RC File from the DRA OpenStack Dashboard via Project -> API Access -> Download OpenStack RC File
# Store your DRA Project credentials as environment variables with the downloaded shell script
source <project name>-openrc.sh
# Start uploading files/directories to your object storage container/bucket
swift upload <your_container_name> <path_to_directory>
```

## QGIS - Accessing Objects (Files) in a Private Container/Bucket

While any data stored in a public container/bucket can easily be accessed and
imported into QGIS using an HTTPS URL, private data can also be accessed given
QGIS has access to your object storage credentials.

### OpenStack Swift

Similarly to using the OpenStack Swift client, you'll need to download your
OpenStack RC file from the dashboard by navigating to Project -> API Access ->
Download OpenStack RC File. The RC file will include important and sensitive
authentication information so be sure to properly secure it. You will need to
extract the environment variables held in this file and enter them into QGIS by
opening Settings -> Options... -> System -> Environment. Be sure to check the
box to use custom variables and start copying in the variables from the RC file.

![QGIS Settings with custom environment variables](/assets/images/qgis_s3.PNG)

Once you have copied your credentials, you will need to restart QGIS. You can
then load a file from your OpenStack container by adding the layer using the
OpenStack Swift Object Storage protocol type along with providing the name of
the container in which the file is stored and the name of the file as the object
key (note: if the file is stored in a subdirectory, the name of the directory
will need to be included)

### S3-Compatible

The process for using an S3-compatible object storage provider, is similar to
that listed above, but instead of using an OpenStack RC file and environment
variables, you will need to set the following custom environment variables in
QGIS, which can be attained from any S3-compatible object storage provider.

- AWS_SECRET_ACCESS_KEY
- AWS_ACCESS_KEY_ID

Finally, while importing your file as a layer, you will need to use the AWS S3
protocol type.

## Commercial Cloud Object Storage Providers

If neither the Alliance Cloud or Chinook provide sufficient features or you plan
on using a particular cloud computing service that is only available through a
commercial cloud provider, you can access object storage directly through
commercial cloud providers.

Contact
[UBC ARC](https://arc.ubc.ca/compute-storage/cloud-computing){target="\_blank"}
to get details about accessing credits that can mitigate costs associated with
using the following cloud providers.

- [AWS S3](https://docs.aws.amazon.com/s3/){target="\_blank"}

- [Google Cloud Storage](https://cloud.google.com/storage/docs/){target="\_blank"}

- [Microsoft Azure Blob Storage](https://learn.microsoft.com/en-us/azure/storage/blobs/){target="\_blank"}

If you are working with an organization outside of UBC and/or are unable to
access credits to help cover the costs of object storage, the following
providers have generous free tiers and generally lower pricing options.

- [Cloudflare R2](https://developers.cloudflare.com/r2/){target="\_blank"}

- [Backblaze B2](https://www.backblaze.com/docs/cloud-storage){target="\_blank"}
