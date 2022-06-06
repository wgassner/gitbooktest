# Archiving

## What? <a href="#what" id="what"></a>

Export law or the GDPR defined a certain amount of time denied party screening shall be available for audits and controls. Once the time limit is reached data can be archived and/or deleted.

The archived data includes:

* [Sanction Lists](https://miccust.sharepoint.com/sites/ProductDocumentationECM/SitePages/Sanction-List.aspx)
* [Black Lists](https://miccust.sharepoint.com/sites/ProductDocumentationECM/SitePages/Black-List.aspx)
* [Positive Lists](https://miccust.sharepoint.com/sites/ProductDocumentationECM/SitePages/Positive-List.aspx)
* [White Lists](https://miccust.sharepoint.com/sites/ProductDocumentationECM/SitePages/White-List.aspx)
* [Screening Requests](https://miccust.sharepoint.com/sites/ProductDocumentationECM/SitePages/Screening-Request.aspx) (with results and parties)

### Archiving unused data <a href="#archiving-unused-data" id="archiving-unused-data"></a>

Before the delete operation, the data are moved to the expiration state. This means that any screening will not result in a match.

However, depending on the numbers of entities and their frequency to be screened this may result in a very large database.

MIC-ECM will provide functionality for removing data from the production database to external storage or data warehouse systems (like MIC data analytics).

If for example a positive list entry should be deleted it will be set to "**expired**" instead. Each entry has a valid from and valid to date. In the expiration process, the **valid to** date will be set to the current date and time.

The ECM user can still see these entries opening the positive list entries and enabling the "**Show History**" of the filter.

### Delete expired data <a href="#delete-expired-data" id="delete-expired-data"></a>

A delete job is available to remove the unused data that is not used anymore.

## Why? <a href="#why" id="why"></a>

GDPR (or DSGVO in German) requires to delete data after years. Besides that, expired data are also not required after this period. Furthermore, keeping unused data requires more memory.

## Who? <a href="#who" id="who"></a>

automatic job that will be started every 6 months (half year).

## How? <a href="#how" id="how"></a>

### Prerequisities: <a href="#prerequisities" id="prerequisities"></a>

* [Screening Lists](https://miccust.sharepoint.com/sites/ProductDocumentationECM/SitePages/Screening-List.aspx) are set up
* Job can be executed

see the job description: [cleanUpDPS](https://miccust.sharepoint.com/sites/ProductDocumentationECM/SitePages/ECM-DPS-Jobs.aspx#description)

## Additional Information <a href="#additional-information" id="additional-information"></a>

see the following [concept](https://miccust.sharepoint.com/sites/MICECMProductSpace/Shared%20Documents/General/Analysis/Archiving%20Concept/Concept%20Archiving%20in%20MIC-ECM.docx?web=1).
