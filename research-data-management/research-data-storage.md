---
title: Research Data Storage
---

This document lists current data storage options available to UBC Geography
researchers and could be consulted when developing Data Management Plans for new
research projects. For information and/or consultation about Research Data
Management and developing a Data Management Plan, check out
[UBC Library RDM](https://researchdata.library.ubc.ca/) or
[UBC Advanced Research Computing](https://rdm.ubc.ca/). For questions about
these data storage options and how best to integrate them with your data
collection processes, contact
[UBC Geography IT](https://geog.air.arts.ubc.ca/services/computing-services/).

UBC Library's Research Data Management team, recommends the following:

- You should have at least **3** copies of your data

  - The **here** copy, which can be your working copy.

  - The **near** copy, which is a local backup. Perhaps an external hard drive.

  - The **far** copy that is stored off-site and ideally accessible from a
    computer other than yours.

- The copies should be stored in 2 different locations, like your backup disk
  and the cloud. Please don't put two extra copies on the same backup disk!

The storage location for each copy of your data will depend on the nature of
your project, with specifics determined by how and where data will be collected
and/or analyzed.

The 'here copy' can be anywhere that your data is initially collected. Common
examples include:

- the hard drive on your laptop or workstation,

- a folder within your UBC OneDrive account,

- a volume connected to a server,

- or an S3 storage bucket within a cloud provider.

A 'near copy' should provide an easy, reliable, and preferably automated process
for backing up the data in your 'here copy.' Common examples include:

- an external hard drive connected to your laptop,

- a secondary drive/disk within your workstation or desktop,

- or a cloud storage location that is synchronized with your local drive.

UBC Geography IT can provide support in selecting and acquiring an external hard
drive or installing a secondary disk on your desktop machine.

'Far copies' are often stored in 'cloud' servers, where the servers are off-site
from the 'here' and 'near' copies. If you are already using a 'cloud' provider,
like OneDrive, to store your 'here' and 'near' copies, backup the data to a
local storage device or another external 'cloud' provider. While 'cloud' storage
includes a high-level of redundancy with multiple off-site backups already in
place, backing up your data from 'cloud' storage guarantees additional
protections from catastrophic failure.

If you do not plan on using High Performance Computing to run resource intensive
computations on your data, need less than 1 TB of storage, and do not anticipate
storing any files above 15 GB, your UBC OneDrive account should be able to cover
your needs. If you are using Windows, OneDrive is likely already installed on
your device. Mac is also supported with instructions
[here.](https://support.microsoft.com/en-us/office/sync-files-with-onedrive-on-macos-d11b9f29-00bb-4172-be39-997da46f913f)
Use this [link](https://arc.ubc.ca/microsoft-onedrive-and-teams-research) to
learn more about using OneDrive and other Microsoft cloud services for data
storage. You can also view this
[document](https://it.ubc.ca/sites/it.ubc.ca/files/UBC%20Online%20Storage%20Solutions%20-%20Features%20Comparison%20Chart.pdf)
to see a feature comparison of UBC's online storage solutions.

If you do plan to run resource intensive computations on your data or plan on
storing more than 1 TB of data, consider applying for resource allocations from
either UBC Advanced Research Computing or the Digital Research Alliance. Your
data can then be stored and easily analyzed using High Performance Computing
resources.

## HPC Options for UBC Faculty

### UBC Chinook

Documentation: <https://confluence.it.ubc.ca/display/UARC/Using+Chinook>

Eligibility:

- Minimum: UBC Faculty or UBC Principal Investigator

- Priority:

  - New to UBC

  - In first 5 years of career

  - Data must be stored on-site and can't be accommodated by other resources
    (e.g. Digital Research Alliance)

Application: <https://arc.ubc.ca/apply-chinook>

Allocation Renewal: Annual

Locations:

- UBC Vancouver

- UBC Okanagan

Storage Quota:

- Minimum Request: 1 TB

- Maximum Request: None

File Size Limit: 5 TB

Data Transfer and Sharing Services: Globus

Transfer Limits: Set by
[Globus](https://docs.globus.org/faq/transfer-sharing/#are_there_any_limits_on_using_the_file_transfer_service)

Supported Computing Software for HPC Data Analysis via UBC Sockeye:
<https://confluence.it.ubc.ca/display/UARC/Software>

### Digital Research Alliance

Documentation: <https://docs.alliancecan.ca/wiki/Storage_and_file_management>

Eligibility: Academic faculty in Canada

Application:

- Account:
  <https://alliancecan.ca/en/services/advanced-research-computing/account-management/apply-account>

- RAS (Rapid Access Service -- for fast allocations up to 10 TB):
  <https://alliancecan.ca/en/services/advanced-research-computing/accessing-resources/rapid-access-service>

- Resource Allocation Competition:
  <https://alliancecan.ca/en/services/advanced-research-computing/accessing-resources/resource-allocation-competition>

  - Submission Start: Late September

  - Submission End: Early November

  - Announcements: Late March

  - Implementation: Early April

Allocation Renewal: Annual

Locations:

- SFU Burnaby (Cedar)

- UW Waterloo (Graham)

- McGill Montreal (Béluga)

- UT Toronto (Niagra)

Storage Quota:

- Minimum:

  - Home: 50 GB per user

  - Project: 1 TB per group

  - Nearline (Cold storage): 2 TB per group

- Maximum Request:

  - Via Rapid Access Service: 10 TB

  - Via Resource Allocation Competition: None

Data Transfer and Sharing Services: Globus

Alternative Transfer Options:
<https://docs.alliancecan.ca/wiki/Transferring_data>

Supported Computing Software via ARC Clusters:
<https://docs.alliancecan.ca/wiki/Available_software>
