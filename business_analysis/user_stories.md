## NOT CURRENT - UNDER RECONSTRUCTION - Introduction

These are draft user stories for the human omics research data infrastructure under development as part of the GUARDIANS Program at QIMR Berghofer. They reflect both work that QIMRB is already engaged in, and the ambitions of the project team and users for the feature set and functionality of the system to be delivered. Important caveats:

* This is absolutely not an exhaustive list, and is not in order of importance.

* There are varying levels of granularity here. Some are epic-level system stories. Some are nearly feature-level user stories. 

* This is a living document to be updated as more discovery comes to light.

* We’ve taken a maximalist interpretation of the concept of ‘user’: as someone that interacts with the system in some capacity. Importantly, this includes the design, development, and operation of systems as well as ‘consumer-level’ interactions.

---

## User Stories

| ID | Requirement type | Category | As a (Applicable Persona) | I want | so that | Value/Priority | Capability |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| US1 | Functional | Data Access Request | Data Custodian | to understand what the researcher is seeking to explore with the data | it increases the opportunity for them to find what they need, to make the best use out of it and to potentially create a collaborative relationship. |  |  |
| US2 | Functional | Publication Tracking and Data Access Reporting | Data Custodian | to be appropriately acknowledged for the supply of data | we can report to our funders and demonstrate additional impact from the data. |  |  |
| US3 | Functional | Data Access Request | Data Custodian | an opportunity to create collaborations (through learning more about the data applicant) | I can be included as a co-author on published papers arising from the accessed data. |  |  |
| US4 | Functional | Publication Tracking and Data Access Reporting | Data Custodian | to know who is getting access to our data | we can demonstrate the impact of our data holdings. |  |  |
| US5 | Functional | Data Access Request Management | Data Custodian | to manage data access requests in a dedicated system with web interface and messaging | we can track and store documented data access request decisions in one reliable place. |  |  |
| US6 | Functional | Data Discovery Solution | Researcher | to get a curated subset of the available data through collaboration with the data owner | I can answer a specific research question. |  |  |
| US7 | Functional | Medical Ontology | Researcher | to see medical ontology for each dataset in the data commons | I apply for and access the most suitable data. |  |  |
| US8 | Functional | Consent, Ethics and Data Use Ontology | Researcher | to use DUO codes to check what data is consented for | when I select and apply for data, I am confident that ethically, I can use it. |  |  |
| US9 | Functional | Data Access Request Management | Researcher | to apply via web interface for data access | I can track the progress of my application efficiently. |  |  |
| US10 | Functional | Data Access Request Management | Researcher | to receive approvals, refusals, requests for more information via web/messaging | I can track the progress of my application efficiently. |  |  |
| US11 | Policy | Consent and Ethics | Data Governance Officer, Business Development Office | to ensure that the appropriate DTA can be put in place between the researcher's organisation and QIMRB and that the appropriate person in authority at the researcher's organisation has signed off on it | we are not in breach of NHMRC or QIMRB or data ethics and sharing conditions. |  |  |
| US12 | Policy | Consent and Ethics | Data Governance Officer | to ensure ethics is in place and communicated for sharing, for example: not for commercial | we are not in breach of NHMRC or QIMRB or data ethics and sharing conditions. |  |  |
| US13 | Functional | Data Discovery | Researcher | to discover and navigate a data catalog hosted on Beacon | I can get information about the datasets that may be useful for my project. |  |  |
| US14 | Functional | Data Access Request Management | Data Governance Officer | continuity thru the systems where you have a start point for request thru the endpoint for release | the data custodians can track, record keep. |  |  |
| US15 | Functional | Data Access Request Management | Data Governance Officer | appropriate records and logs in the data access request system | justification of decision making and for reporting. |  |  |
| US16 | Functional | Data Management | Researcher | to use a Tier 3 EGA repository to access Australian data in Australia | I can save months in the process of data application and download compared to downloading from Europe. |  |  |
| US17 | Functional | Data Quality and Metadata | Researcher | to see a minimum standard of data quality information in the metadata: e.g. read depths, or number of reads sequenced, library type as a minimum quality control description | I don't have to apply for and then download something before discovering its quality is not acceptable. |  |  |
| US18 | Functional | Data Quality and Metadata | Research Team Leader (related to US17 above) | to see a minimum quality control description standardised for human genome data in Australia | researchers in my team can find acceptable quality data quickly and easily and more often. |  |  |
| US19 | Important non technical deliverables  | Education and Communication | Research Team Leader | education resources provided to my organisation's other divisions on how to create appropriate participant/donor consent forms | reduce the load on more experienced teams who currently coach 1 on 1 those within the organisation who need to set up data collection and sharing. |  |  |
| US20| Important non technical deliverables | Education and Communication |Genome Informatics Sys Admin | researchers to understand the need to maintain data anonymity and encryption | reduce the need for me to provide one-on-one education and to ensure patient privacy is protected. |  |  |  
| US21 |  |  |  |  |  |  |  |
| US22 |  |  |  |  |  |  |  |
| US23 |  |  |  |  |  |  |  |
| Future Phase |  | Data Access Request Management | Researcher | ***This user story has a heavy dependency on high quality metadata and also on a future capability for htsget to support encrypted files (currently supports only unencrypted):*** I want to be able to order a slice of data and take it away \- for example I want the variant data for 3000 genes | ***Rather than the so that part of the statement \- this statement describes how the capability could be delivered \- making a baby BAM file, enabled by htsget, in a future where htsget supports encrypted files and there is excellent patuent metadata available.*** |  |  |
---

## Glossary for a Human Data Sharing System
| **Term** | **Definition** |
| :---- | :---- |
|**Application Service Provider** | Entity that provides application services, such as web-based or mobile clients, for manipulating and analysing data using agreed standards (see **Data Processor** below). |
| **Authorised** | Granted conditional permission to use a resource (data or compute). |
| **Clinical Research Coordinator** | A Clinical Research Coordinator (CRC) manages and conducts the day-to-day activities of a clinical trial. |
| **Compute Resource**  | For example: an analysis platform, managed workflow service, or general-purpose compute environment. These resources may be distinguished by: in-theory unbounded resource requirements of single-user jobs, and/or non-linear marginal cost to supply additional demand. For example, an online catalog service is not a compute resource. |
| **Compute Resource Provider** | Provider or administrator of a compute resource. Whether on-prem or in the cloud, ultimately they foot the bill — which may or may not be passed on to **Data User(s)**. |
| **Data** | In the context of these user stories, Data is defined as information in structured and unstructured formats, provided by **Participants**, as distinguished from data about users of the **Data Sharing System**.| 
| **Data Contributors** | Entities who make their data available for use within the **Data Sharing System**. These include **Participants** and **Data Owners** (both separately defined here). |
| **Data Controller** | The legal entity, person or agency to which **Data Contributors** delegate the responsibility of ensuring the integrity and quality of data made available to the Data User community, and of guaranteeing that data management is consistent with community standards, applicable law, institutional policy, and individual permissions. |
| **Data Custodian** | A role responsible for one or more aspects of safe custody, transport and storage of data, and implementation of business rules and/or the technical environment to control access. Job titles with some data custodian responsibilities may include system administrator, database administrator, dev/ops or data engineer. |
| **Data Governance Officer** | A role responsible for ensuring data quality and fitness for purpose of the organization's data assets, and for implementation of governance. They ensure data quality, accuracy, and adherence to business rules and policies. May also be known as a **Data Steward**.|
| **Data Owner** | The legal persons, agencies or bodies to which participants delegate the authority to decide on the access and usage of their data. |
| **Data Processor** | The entity that processes the data provided by **Data Contributors** according to the business and security policies set by **Data Controllers**, and which puts in place all the needed technical safeguards to enforce them. Types of Data Processor include **Infrastructure Service Providers**, **Data Service Providers** and **Application Service Providers** (separately defined here). |
| **Data Service Provider** | Entity that provides data storage, protection, management, access, and transmission services to the Data User community, and optionally ensure that data transmitted or uploaded to other destinations are qualified according to the specifications for both data and metadata quality, access constraints, and semantics, as appropriate (see **Data Processor**). |
| **Data Sharing System** | The system to be built for the sharing of data, including its technical elements, policies, procedures and supporting infrastructure. |
| **Data User** | An individual or group that accesses and uses data for various purposes, such as research. (See **Researcher** separately defined below.) |
| **General-purpose Compute Environment** | e.g. HPC, low-level cloud compute services e.g. AWS EC2, Batch. |
| **Infrastructure Service Provider** | Entity that provides technology resources and technical support for persisting, protecting, managing, accessing, transmitting, and using electronic data; they include both enterprise and cloud service providers (see **Data Processor**). |
| **Managed Workflow Service** | e.g. Seqera, Terra. |
| **Participants** | People who allow their genomic, health-related and/or other relevant data to be used and shared, within the bounds of the consent they have granted. |
| **Researcher** | A (potential) consumer of the data and/or compute resources available in the ecosystem. Researchers will usually have questions or studies that may benefit from access to the data. |
| **Trusted Research Environment** | A compute environment set up for research with sensitive data that has built-in security controls and user access management features. The [SARTRE](https://satre-specification.readthedocs.io/en/stable/faqs.html#what-tre) spec has detailed guidance on what constitutes a TRE. |
---

