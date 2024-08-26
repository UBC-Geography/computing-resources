---
title: Research Data Storage
tbl-cap-location: top
---

UBC researchers have access to multiple options for their research data.
Selecting a storage option can be dependent on the nature of the data itself
(privacy and size) along with the location of research collaborators, personal
preferences, and processes used for data collection. When developing a
[Data Management Plan (DMP)](https://rdm.ubc.ca/support-services/data-management-plans),
consider all of these factors when selecting the best options for your research.

For information and/or consultation about Research Data Management (RDM) and
developing a DMP, check out
[UBC Library RDM](https://researchdata.library.ubc.ca/) or
[UBC Advanced Research Computing](https://rdm.ubc.ca/). For initial questions
about data storage options and how best to integrate them with your data
collection processes, contact
[UBC Geography IT](https://geog.air.arts.ubc.ca/services/computing-services/).

UBC Library's Research Data Management team, recommends the following:

> You should have at least **3** copies of your data
>
> - The **here** copy, which can be your working copy.
>
> - The **near** copy, which is a local backup. Perhaps an external hard drive.
>
> - The **far** copy that is stored off-site and ideally accessible from a
>   computer other than yours.
>
> The copies should be stored in 2 different locations, like your backup disk
> and the cloud. Please don't put two extra copies on the same backup disk!

The storage location for each copy of your data will depend on the nature of
your project, with specifics determined by how and where data will be collected
and/or analyzed.

The 'here copy' can be anywhere that your data is initially collected. Common
examples include:

- the hard drive on your laptop or workstation,

- a volume connected to a virtual machine,

- or an object storage bucket on cloud provider's infrastructure.

A 'near copy' should provide an easy, reliable, and preferably automated process
for backing up the data in your 'here copy.' Common examples include:

- an external hard drive connected to your laptop,

- a secondary drive/disk within your workstation or desktop,

- a local Network Attached Storage drive located in your office or lab,

- a UBC provided network attached drive, like
  [UBC Home Drive](https://it.ubc.ca/services/web-servers-storage/home-drive-storage-service)
  or
  [UBC TeamShare](https://it.ubc.ca/services/web-servers-storage/home-drive-storage-service),

UBC Geography IT can provide support in selecting an external hard drive for
your laptop or installing a secondary disk on your desktop.

'Far copies' are often stored in 'cloud' servers, where the servers are off-site
from the 'here' and 'near' copies. If you are already using a 'cloud' provider,
like OneDrive, to store your 'here' and 'near' copies, backup the data to a
local storage device. While 'cloud' storage includes a high-level of redundancy
with multiple off-site backups already in place, backing up your data from
'cloud' storage guarantees additional protections from various types of
catastrophic failure.

| Service                                                                                                  | Storage per User | Storage per Allocation   | Costs                         |
| -------------------------------------------------------------------------------------------------------- | ---------------- | ------------------------ | ----------------------------- |
| [UBC Home Drive](https://it.ubc.ca/services/web-servers-storage/home-drive-storage-service)              | 20-100 GB        |                          | 20 GB free then $0.35/GB/year |
| [UBC OneDrive](https://it.ubc.ca/services/web-servers-storage/microsoft-onedrive)                        | 1 TB             |                          | None                          |
| [UBC TeamShare](https://it.ubc.ca/services/web-servers-storage/home-drive-storage-service)               |                  | 20 GB or more            | $0.15/GB/year                 |
| [ARC Sockeye](https://confluence.it.ubc.ca/display/UARC/About+Sockeye#AboutSockeye-StorageVolumes)       | 50 GB            | 5 TB+                    | None                          |
| [ARC Chinook](https://confluence.it.ubc.ca/display/UARC/About+Chinook)                                   |                  | Determined by allocation | None                          |
| [Alliance NextCloud](https://docs.alliancecan.ca/wiki/Nextcloud)                                         | 50 GB            |                          | None                          |
| [Alliance HPC](https://alliancecan.ca/en/services/advanced-research-computing/national-services/storage) | 50 GB            | 1 TB+                    | None                          |
| [Alliance Cloud Arbutus Object](https://docs.alliancecan.ca/wiki/Arbutus_object_storage)                 |                  | 1 GB+                    | None                          |
| [Alliance Cloud Virtual Machine](https://docs.alliancecan.ca/wiki/Working_with_volumes)                  |                  | 20 GB+                   | None                          |

: Network, Cloud, and HPC Storage {.striped .table}

<br>

A common and cost-effective setup for researchers that are collecting data on
their local machine, includes downloading the OneDrive desktop client, setting
up automatic synchronization on any folders that contains research data,
connecting a second drive to the machine, and running either daily or weekly
backups onto the secondary drive.

For use cases, where the overall amount of data being collected and analyzed
nears or exceeds 1TB, contact Geography IT about setting up a RAID array with
your local machine and submitting a request to either UBC ARC or the Digital
Research Alliance for an allocation of HPC/object storage.
