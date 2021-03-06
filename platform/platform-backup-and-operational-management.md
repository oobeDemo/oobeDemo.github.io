# Platform Backup and Operational Management

## RPO, RTO and retention periods

As with an on-premises environment, backups play an important part of an overall cloud solution capability. It is important that critical information is backed up to enable recovery for scenarios such as accidental deletion or corruption.

To ensure a successful backup, configuration of the following items should be taken into consideration:

* What to backup - understanding what configuration, files and mailboxes that need to be backed up is important. If only a partial configuration is backed up, successful restoration may not be possible.
* Recovery Point Objective \(RPO\) - RPO defines an acceptable loss of data \(in time\) for a data type in a data-loss event. RPOs are expressed in hours / days and directly influence the backup approach used, and how backups are performed with sufficient frequency to meet the defined RPO. For example, if an RPO of 12 hours was defined for a given data type, backups of this data type could not be scheduled further than 12 hours apart.
* Recovery Time Objective \(RTO\) - RTO is used to define the acceptable level of service interruption \(in time\) between a data loss event and the recovery of the data to a point at which normal service is resumed. When determining RTOs for a given data type, consideration must also be given to any additional recovery process that are undertaken after the restoration of data. The RTO directly influences the type of backups performed and may dictate additional protection mechanisms outside of the backup platform for data types where a very short RTO is defined.
* Legislative Requirements – The essential 8 details that backups of important information, software and configuration settings are performed. More detail on these controls are listed in the [Protective Security Policy Framework](https://www.protectivesecurity.gov.au/sites/default/files/2019-11/pspf-infosec-10-safeguarding-information-cyber-threats.pdf) and the [Essentail Eight Matruity Model](https://www.cyber.gov.au/acsc/view-all-content/publications/essential-eight-maturity-model).

It is important that prior to defining the backup and restore policies, RTO and RPO objectives for each data type hosted the environment are defined in line with business requirements and Service Level Agreements \(SLA\).

There are several enterprise Backup software solutions which can backup data on-premises or in the cloud. Depending on the requirements, a backup solution can cover the following scenarios:

* Backup local data directly to on-premises infrastructure from on-premises.
* Backup local data to on-premises infrastructure and to the Azure storage blob from on-premises.
* Backup cloud data directly from the cloud.

Using the native Office 365 tools only, in combination with recycle bins the following data recovery options and retention periods are available:

* What to backup - understanding what configuration, files and mailboxes that need to be backed up is important. If only a partial configuration is backed up, successful restoration may not be possible.
* Documents, Desktops and Pictures for each user is redirected from the Windows client device to OneDrive using Windows Known Folders providing a backup of data to the cloud.
* OneDrive includes recycle bins allowing recovery of data for up to 93 days.
* SharePoint Online data includes recycle bins allowing recovery of data for up to 93 days.
* Teams chat, channel and files data retained indefinitely by default unless retention policies have been implemented.
* Exchange Online has a recover deleted items from server option allowing recovery of data for up to 30 days.

Retention policies are created that ensure that data is retained forever for:

* Exchange
* SharePoint
* OneDrive
* Microsoft 365 groups
* Skype for Business
* Exchange Public Folders
* Teams channel messages
* Teams chats

Workstation configuration is stored in Intune. \(AutoPilot rebuild\).

When deploying a hybrid solution, the cloud based native Office 365 tools will not meet an Agencies requirement for on-premises and cloud backups. Agencies will need to investigate third party backup solutions which can backup data on-premises or in the cloud.

RPO, RTO and Retention Periods Design Decisions for all agencies and implementation types.

| Decision Point | Design Decision | Justification |
| :--- | :--- | :--- |
| Online Exchange Mailboxes | RPO – 24 hours from backup or better RTO - &lt; 48 hours or better | RPO and RTO in relation to cloud backups is for guidance only. Agencies are required to measure these against the business, application, regulatory and security requirements. |
| Online Exchange Mail Items | RPO – 24 hours from backup or better RTO - &lt; 48 hours or better | RPO and RTO in relation to cloud backups is for guidance only. Agencies are required to measure these against the business, application, regulatory and security requirements. |
| Online SharePoint | RPO – 24 hours from backup or better RTO - &lt; 48 hours or better | RPO and RTO in relation to cloud backups is for guidance only. Agencies are required to measure these against the business, application, regulatory and security requirements. |
| Teams | RPO – 24 hours from backup or better RTO - &lt; 48 hours or better | RPO and RTO in relation to cloud backups is for guidance only. Agencies are required to measure these against the business, application, regulatory and security requirements. |
| OneDrive for Business | RPO – 24 hours from backup or better RTO - &lt; 48 hours or better | RPO and RTO in relation to cloud backups is for guidance only. Agencies are required to measure these against the business, application, regulatory and security requirements. |

Additional RPO, RTO and Retention Periods Design Decisions for cloud native implementations

| Decision Point | Design Decision | Justification |
| :--- | :--- | :--- |
| Restoration tools | Microsoft backup and restoration tools | The Agency will leverage Microsoft Office 365 native tools in the first instance to recover user data. |
| Items to Backup | Exchange Online SharePoint Online Microsoft Teams OneDrive for Business Microsoft 365 groups | Backups must cover the Microsoft suite of tools at a minimum. |
| Retention Policies | Up to maximum allowable days per Microsoft Office 365 application | For guidance only. Agencies are required to measure these against the business, application, regulatory and security requirements. |

Additional RPO, RTO and Retention Periods Design Decisions for hybrid implementations

| Decision Point | Design Decision | Justification |
| :--- | :--- | :--- |
| Restoration tools | Third party backup and restoration tools | Agencies should investigate third-party backup tools to backup and restore data on-premises and within the cloud. |
| Items to Backup | Exchange Online SharePoint Online Microsoft Teams OneDrive for Business Microsoft 365 groups On-premises Exchange On-premises SharePoint | Backups must cover the Microsoft suite of tools at a minimum. |
| Retention Policies | At discretion of Agency | Retention policies for the backups should be determined by the Agency and measured against the business, application, regulatory and security requirements. |

## Data availability

Microsoft Azure services are available globally and provides geographical, regional, data centre, virtual infrastructure, and application resiliency. This allows the Microsoft Azure platform and Office 365 to combat and minimise potential disasters such as customers loss of connectivity to data or loss of data.

Data availability is an important part of making sure that end users have access to the data when they require it. The cloud-based service of Microsoft Office 365 will replicate and store Agency's data in multiple data centres which are geographically dispersed \(see [Exchange data resiliency](https://docs.microsoft.com/en-us/office365/enterprise/office-365-exchange-data-resiliency) and [Office 365 data resiliency](https://docs.microsoft.com/en-us/office365/Enterprise/office-365-data-resiliency-overview)\). The Office 365 applications that provide this data availability are:

* Exchange
* SharePoint
* OneDrive
* Teams

The data availability and resiliency of Office 365 cloud service is in-built and managed by Microsoft.

Data Availability Design Decisions for all agencies and implementation types.

| Decision Point | Design Decision | Justification |
| :--- | :--- | :--- |
| Data Availability | Configured | Microsoft have in-built data availability into the Office 365 cloud services. |

