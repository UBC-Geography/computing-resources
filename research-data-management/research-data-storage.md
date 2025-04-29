---
title: Research Data Storage
# change to date to last-modified after next modification
date: 2025-04-09
tbl-cap-location: top
---

UBC researchers have access to multiple options for their research data.
Selecting a storage option can be dependent on the nature of the data itself
(privacy and size) along with the location of research collaborators, personal
preferences, and processes used for data collection. When developing a
[Data Management Plan (DMP)](https://rdm.ubc.ca/support-services/data-management-plans){target="\_blank"},
consider all of these factors when selecting the best options for your research.

For information and/or consultation about Research Data Management (RDM) and
developing a DMP, check out
[UBC Library RDM](https://researchdata.library.ubc.ca/){target="\_blank"} or
[UBC Advanced Research Computing](https://rdm.ubc.ca/){target="\_blank"}. For
initial questions about data storage options and how best to integrate them with
your data collection processes, contact
[UBC Geography IT](https://geog.air.arts.ubc.ca/services/computing-services/){target="\_blank"}.

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
  [UBC Home Drive](https://it.ubc.ca/services/web-servers-storage/home-drive-storage-service){target="\_blank"}
  or
  [UBC TeamShare](https://it.ubc.ca/services/web-servers-storage/home-drive-storage-service){target="\_blank"},

UBC Geography IT can provide support in selecting an external hard drive for
your laptop or installing a secondary disk on your desktop.

'Far copies' are often stored in 'cloud' servers, where the servers are off-site
from the 'here' and 'near' copies. If you are already using a 'cloud' provider,
like OneDrive, to store your 'here' and 'near' copies, backup the data to a
local storage device. While 'cloud' storage includes a high-level of redundancy
with multiple off-site backups already in place, backing up your data from
'cloud' storage guarantees additional protections from various types of
catastrophic failure.

| Service                                                                                                                    | Storage per User | Storage per Allocation   | Costs                         |
| -------------------------------------------------------------------------------------------------------------------------- | ---------------- | ------------------------ | ----------------------------- |
| [UBC Home Drive](https://it.ubc.ca/services/web-servers-storage/home-drive-storage-service){target="\_blank"}              | 20-100 GB        |                          | 20 GB free then $0.35/GB/year |
| [UBC OneDrive](https://it.ubc.ca/services/web-servers-storage/microsoft-onedrive){target="\_blank"}                        | 1 TB             |                          | None                          |
| [UBC TeamShare](https://it.ubc.ca/services/web-servers-storage/home-drive-storage-service){target="\_blank"}               |                  | 20 GB or more            | $0.15/GB/year                 |
| [ARC Sockeye](https://confluence.it.ubc.ca/display/UARC/About+Sockeye#AboutSockeye-StorageVolumes){target="\_blank"}       | 50 GB            | 5 TB+                    | None                          |
| [ARC Chinook](https://confluence.it.ubc.ca/display/UARC/About+Chinook){target="\_blank"}                                   |                  | Determined by allocation | None                          |
| [Alliance NextCloud](https://docs.alliancecan.ca/wiki/Nextcloud){target="\_blank"}                                         | 50 GB            |                          | None                          |
| [Alliance HPC](https://alliancecan.ca/en/services/advanced-research-computing/national-services/storage){target="\_blank"} | 50 GB            | 1 TB+                    | None                          |
| [Alliance Cloud Arbutus Object](https://docs.alliancecan.ca/wiki/Arbutus_object_storage){target="\_blank"}                 |                  | 1 GB+                    | None                          |
| [Alliance Cloud Virtual Machine](https://docs.alliancecan.ca/wiki/Working_with_volumes){target="\_blank"}                  |                  | 20 GB+                   | None                          |

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

When initially requesting storage in the HPC systems, these are our general
recommended steps to move through as your storage needs increase.

1. Setup an account with the
   [Alliance](https://alliancecan.ca/en/services/advanced-research-computing/account-management/apply-account){target="\_blank"}.
   This will provide you with
   [1TB of project storage](https://alliancecan.ca/en/services/advanced-research-computing/national-services/storage){target="\_blank"}
   on the Alliance clusters, and you can store your data on the Cedar cluster in
   Burnaby for the lowest latency to UBC Vancouver. Additionally, your account
   will be provided access to 20 TB of temporary storage in a scratch directory
   and 2 TB for backup storage.

2. Ask collaborators, including research assistants, to apply for Alliance
   accounts as well. For students and staff, they'll need to list you as a
   sponsor, and then they'll get access to the cluster and your project's
   storage directory, which they will have read and write access to.

3. When you start needing more storage, apply through the Alliance's
   [Rapid Access Service (RAS)](https://alliancecan.ca/en/services/advanced-research-computing/accessing-resources/rapid-access-service){target="\_blank"}
   application noting how much more storage you anticipate needing. The
   application can be submitted at any time during the year, and you can keep
   submitting the application as your storage needs increase until you've been
   allocated 40 TB of project storage.

4. Once you storage needs start getting towards 40 TB, then you should strongly
   consider contacting the folks at UBC ARC for
   [consultation](https://arc.ubc.ca/consultation){target="\_blank"}. Further
   requests for storage will need to be submitted through the Alliance's annual
   [Resource Allocation Competition (RAC)](https://alliancecan.ca/en/services/advanced-research-computing/accessing-resources/resource-allocation-competition/resource-allocation-competition-application-guide){target="\_blank"}.

UBC ARC's cluster, Sockeye, is meant to fill any gaps left behind by the
Alliance clusters, so if you need to keep your data specifically on UBC
Vancouver campus or if for any other reason the Alliance clusters can't meet the
needs of your project, you can apply for an allocation on that cluster, which
would provide a starting allocation of 5TB, which could be increased as needed.
