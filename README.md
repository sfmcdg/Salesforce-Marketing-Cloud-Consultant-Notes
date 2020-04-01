# Salesforce Marketing Cloud Consultant Notes
> Helpful notes for working through preparation for Salesforce Marketing Cloud consultant exam.

* [How to do discovery with Salesforce Marketing Cloud](#how-to-do-discovery-with-salesforce-marketing-cloud)
* [How conceptual design is implemented in Salesforce Marketing Cloud](#how-conceptual-design-is-implemented-in-salesforce-marketing-cloud)
* [How Marketing Cloud Connect works with Salesforce Marketing Cloud](#how-marketing-cloud-connect-works-with-salesforce-marketing-cloud)
* [How account configuration works with Salesforce Marketing Cloud](#how-account-configuration-works-with-salesforce-marketing-cloud)
* [How reporting works with Salesforce Marketing Cloud](#how-reporting-works-with-salesforce-marketing-cloud)
* [How data design works with Salesforce Marketing Cloud](#how-data-design-works-with-salesforce-marketing-cloud)
* [How emails are built with Salesforce Marketing Cloud](#how-emails-are-built-with-salesforce-marketing-cloud)
* [How automation occurs with Salesforce Marketing Cloud](#how-automation-occurs-with-salesforce-marketing-cloud)
* [How contact builder is used with Salesforce Marketing Cloud](#how-contact-builder-is-used-with-salesforce-marketing-cloud)
* [How Journey Builder is used with Salesforce Marketing Cloud](#how-journey-builder-is-used-with-salesforce-marketing-cloud)


## How to do discovery with Salesforce Marketing Cloud

Configuration in Salesforce Marketing Cloud is flexible and can be adapted to map closely to business and campaign requirements. When making recommendations a key consideration is user expertise and experience with the platform.

### Discovery Process

Set-up of the Marketing Cloud account occurs after purchase. At this stage, Salesforce will have provisioned key aspects of the Marketing Cloud account ready for configuration and  the client will have defined a SOW (Statement Of Work) defining a high-level list of what is required, project-specific activities, deliverables, and timelines for a vendor providing services to the client. 

Using the high-level requirements listed in the SOW a Functional Specification Document (or Blue Print Document) is developed that describes how to achieve the requirements. Functional documentation includes data design in the Marketing Cloud account, data integration and business unit requirements. During enablement of a Marketing Cloud account core configuration can occur. Core configuration includes setup of SAP, RMM, business units, user roles and sender profiles.

### Branding and Creative Strategies

A branding strategy seeks to interact with the customer through a marketing communication. Design is used to strengthen a and convey a consistent message. Tools in the Marketing Cloud that can be employed to help achieve this are:

* **Content templates** - to ensure a consist message is communicated.
* **Approval workflows** - to ensure that only approved communicates are sent.
* **Journey Builder** - used to engage the customer in multi-channel communications.

For campaigns or customer journeys to be implemented information is required about campaign content and how this relates to data stored in the Marketing Cloud account about the subscriber.

Data integration with external systems includes file load for batch processes, APIs for real-time process and the Salesforce connector for CRM. Using these the Marketing Cloud can use data source inputs from external POS, CRM, e-commerce and data warehouse systems.

Considerations for how a campaign will be implemented include frequency, complexity and volume of sending.

## How conceptual design is implemented in Salesforce Marketing Cloud

As a guide considerations for conceptual design in Marketing Cloud should be business structure, data integration and campaign requirements.

### Data considerations

Data model considerations and options:

* **List model** - use the list model for less than 500,000 subscribers, there is a preference for simplicity, fast data loads are not required and there are a limited number of subscriber attributes. Skill set required when using the list model requires confidence with using GUI and drop and drag for configuration and filters.
* **Data extension model** - use the data extension model for greater than 500,000 subscribers, there are multiple subscriber data sets, fast import speeds are required, SOAP/REST APIs required, triggered sends are required and there is a flexible subscription model. Skill set required when using the data extension model requires confidence with using GUI and drop and drag for configuration and filters, and understanding of data relationships and SQL query language.

Data integration options:

* **File import** - use file import to import files from a location into the Marketing Cloud.
* **API** - use SOAP/REST APIs for real-time integration with external systems. APIs includes methods for loading data, triggering notifications and starting communications.
* **Salesforce connector** - use the connector to integrate the Marketing Cloud with Salesforce.

### Campaign considerations

Campaign automation options:

* **TriggerSend** - use a TriggeredSend to send an email on an API request.
* **Automation Studio** - use automation studio to start workflows of tasks that include sending emails or SMS. Automation studio can be triggered using following methods: schedule, changed file in specified location or API. Automation Studio can also be used import files into lists and data extensions, and to execute SQL queries.
* **Journey Builder** - use Journey Builder to send multi-channel campaigns that step the contact through a series of decisions and activities. Journey Builder can be triggered using API, scheduled automation in Automation Studio or Salesforce connector.

### Contact Builder

Contact Builder is used to provide access, builder relationships and link data to the Marketing Cloud account. Contact builder provides a single view of the customer that is used to drive one-to-one messaging.

### IP Warming

IP warming is a strategy to ramp up usage of the IP address so that it is trusted by ISPs and emails are not blocked. During an IP warming strategy initially in week 1 send emails to engaged subscribers with a limit per each ISP (e.g. yahoo, hotmail, gmail, etc.). In week 2 progressively increase sends per ISP. In week 3 and 4 aim at sending more emails per ISP. Throughout watch performance stats closely and pull back sending if any significant issues arise. Refer to [IP Address Warming Guide](https://help.marketingcloud.com/en/documentation/exacttarget/resources/email_deliverability/ip_address_warming_guide/) for guide to limits and quantities of IP warm up sends for each week.

## How Marketing Cloud Connect works with Salesforce Marketing Cloud

For Marketing Cloud Connect prerequisites refer to account and user prerequisites in [Prerequisites & Critical Concepts](https://help.marketingcloud.com/en/documentation/integrated_products__crm_and_web_analytic_solutions/marketing_cloud_connector_v5/connecting_the_clouds/prerequisites__critical_concepts/), in summary:

* **Use a supported Salesforce.com edition with the v5 connector** - includes:  Unlimited, Enterprise, performance and person Accounts. Professional Edition is supported by the v2 connector. Government Cloud requires a custom script to set up a custom domain which must be scheduled 30 days in advance of planned installation. CipherCloud is not supported by Marketing Cloud Connect.
* **Use a supported Salesforce Marketing Cloud account** - includes:  Agency or Agency Client Editions: Core Edition, Advanced Edition, Lock and Publish, Enterprise 2.0 Edition, or Reseller Edition. 
* **Enable Salesforce integration for your Salesforce Marketing Cloud account** - this requires support from Salesforce Marketing Cloud to enable Salesforce Marketing Cloud Connect in the Marketing Cloud account.
* **Administrator credentials/permissions** - obtain administrator credentials for logging in to Salesforce.com and the Salesforce Marketing Cloud.
* **4 custom tabs in Salesforce** - ensure four (4) custom tabs are available in Salesforce.
* **List of integration users** - compile a list of integration users.
* **Create a report in Salesforce** - create a report that defines an intended send to list. Sending to reports requires either a Contact ID or Lead ID.
* **Create a test email in Marketing Cloud** - validate email to ensure that it passes validation.
* **Use recent Chrome or Firefox** - setup is best done with most recent version of Chrome or Firefox.
* **Default Sender Profiles, Delivery Profiles and Send Classification** - ensure that all Default Sender Profiles, Delivery Profiles and Send Classifications have not been deleted or renamed.
* **Users must have license** - license for Marketing Cloud and license for Sales or Service Clouds required with permissions.

### Sending Email

* **Sending an email from Sales or Service Cloud** - to send an email in Sales or Service Cloud:
  1. Click on the Marketing Cloud tab.
  2. Click find in the email row to access Salesforce Marketing Cloud emails.
  3. Click My Emails or Shared Items to view a list of existing Salesforce Marketing Cloud emails.
  4. Proceed to config email to be sent.
* **Sending an email from Marketing Cloud using Send Email in Interactions** - to send an email:
  1. Create a Salesforce Send Email in Interactions.
  2. Select email content.
  3. In recipients select Salesforce reports, Salesforce campaigns, Salesforce Data Extensions, or Salesforce Shared Data Extensions.
  4. Complete remaining fields as required.
  5. Save.
  6. Select the Salesforce Send from the grid and click Send.
* **Sending an email from Marketing Cloud using Guided Send** - to send an email proceed as usual and in recipients select Salesforce Shared Data Extensions.
* **Sending an email from Marketing Cloud using Automation Studio** - create a data filter based on the Salesforce data Extension and then use the filtered data extension in the send activity.

To segment Service Cloud data in Marketing Cloud create a data filter from the Salesforce data extension and then use the drop and drag filter to setup required segmentation.

### Salesforce Marketing Cloud Links

* [#Working notes for doing setup of Salesforce Marketing Cloud V5 data connector](working-nodes-for-setup-of-salesforce-marketingcloud-v5-connector.md)

## How account configuration works with Salesforce Marketing Cloud

### Salesforce Marketing Cloud Roles

Salesforce Marketing Cloud uses [roles](https://help.marketingcloud.com/en/documentation/marketing_cloud/smc_roles/) to manage how the users can access the to application and features. In summary roles consist of:

* **Marketing Cloud Administrator** - allows a person with this role to assist roles to users and manage Mobile Channels Social Channels, Marketing Cloud Apps and Marketing Cloud Tools. Assign a user to the **Marketing Cloud Administrator** role if they want to be able to have access to all features within the marketing Cloud account.
* **Marketing Cloud Viewer** - allows a person with this role to view cross-channel marketing activity that results in Marketing Cloud. Assign a user to the **Marketing Cloud Viewer** if they want to be able to view, but not change or execute campaigns in the Marketing Cloud.
* **Marketing Cloud Channel Manager** - allows a person with this role to create and execute cross-channel interactive marketing campaigns and administer Social and Mobile Channels. Assign a user to the **Marketing Cloud Channel Manager** role if they want to be able to view and create campaigns. A user in this role will not be able to administer users or change configurations.
* **Marketing Cloud Security Administrator** - allows a person with this role to maintain Watchdog security settings and manage user activity and alerts. Assign a user to the **Marketing Cloud Security Administrator** if they want be able to administer users or change configurations. This user has access to MobileConnect and MobilePush, and limited access to email campaigns, automations, content builder and social pages. 
* **Marketing Cloud Content Editor/Publisher** - allows a person with this role to create and deliver messages through Mobile and Sites Channel Apps. Assign a user to the **Marketing Cloud Content Editor/Publisher** role if they want to be able to create and change content.

### Salesforce Marketing Cloud Business Units

A [business unit](https://help.marketingcloud.com/en/documentation/exacttarget/enterprise/enterprise_20_overview/business_units/) is a feature for helping to manage hierarchical structures and data relationships. Business units can mirror workflow processes, demographic and functional structures within the business. Users can be assigned to business units which can help to resolve branding and regulatory compliance considerations. Content and data can be shared accross business units. Business units are a feature of an Enterprise 2.0 marketing Cloud account.

#### Examples of business unit strategies

* **Publication strategy** - an example of a business that uses a publication strategy for business units would be one that is made up of different brands.
* **Demographic strategy** - an example of a business that uses a demographic strategy for business units would be one that operates in different regions or countries.
* **Workflow processes strategy** - an example of a business that uses a Workflow processes strategy for business units would be one that has logical distinctions between business functions.
* **Organisational structure strategy** - an example of a business that uses a organisational structure strategy for business units would be one that has a requirement to map business units to the organisational structure of the business.

### Salesforce Marketing Cloud Reply Mail Management

[RMM (Reply Mail Management)](https://help.marketingcloud.com/en/documentation/exacttarget/admin/reply_mail_management/) allows emails received as replies to campaign sends to be managed. Using RMM Marketing Cloud emails received can automatically be acknowledged and unsubscribe depending on keywords. When setting up RMM there is a one-time requirement to specify a reply subdomain, make the appropriate DNS changes and configure RMM as required. Optional setup includes a triggered send and sender profile.

### Salesforce Marketing Cloud Sender Authentication Package

[SAP (Sender Authentication Package)](https://help.marketingcloud.com/en/documentation/exacttarget/content/sender_authentication_package/) allows the Marketing Cloud to send emails on behalf of the business domain name. SAP includes:

* **Private Domain** - this allows a domain name to be used to send email. This is the domain used on the email from address. Setup includes includes authenticating email sends using the Sender Policy Framework (SPF) and DomainKeys/DKIM authentication.
* **Account Branding** - this allows links and image URLs to use references to the authenticated domain.
* **Dedicated IP Address** - assigns a unique IP address to your account. All email sent from the Marketing Cloud account will use this IP address. IP addresses are part of a successful policy for sender reputation.
* **RMM** - used to manage replies received from subscribers.

## How reporting works with Salesforce Marketing Cloud

> Salesforce Marketing Cloud reporting allow for the marketer to view, access and use reporting data in campaigns.

Reporting options within Salesforce Marketing Cloud include:

* [**Reports**](https://help.marketingcloud.com/en/documentation/reports/getting_started_with_reports/) - used with GUI to generate various send reports.
* [**Data views**](https://help.marketingcloud.com/en/documentation/exacttarget/interactions/activities/query_activity/) - used with queries to update data extensions with subscriber reporting data.
* [**Tracking Extract**](https://help.marketingcloud.com/en/documentation/automation_studio/using_automation_studio_activities/use_a_data_extract_activity/extract_types_reference/) - option in the [Data Extract Activity](https://help.marketingcloud.com/en/documentation/automation_studio/using_automation_studio_activities/use_a_data_extract_activity/) that can be used to export a reporting data file.
* [**Send logging**](https://help.marketingcloud.com/en/documentation/exacttarget/subscribers/send_logging/) - used to log run-time data about sends to a data extension. The send log is an option that needs to enabled in the Marketing Cloud account before use. To create a send log data extension select the `send log` option from templates when creating the send log data extension. The send log data extension can log fields on the data extension used with the send. To log fields ensure that there is a copy of the sendable data extension field required for logging on the send log data extension. This is useful for adding custom fields that are specific to the Marketing Cloud account to a single log of sent data. The send log data extension can be used with queries to help create custom reports.

## How data design works with Salesforce Marketing Cloud

> Salesforce Marketing Cloud allows subscribers data to be stored using a list based model for simple requirements and a relational data model for more complex requirements. The Marketing Cloud relation database can act as a database of record (DBOR) containing centralised storage of information about objects or people.

### Data objects used in Salesforce Marketing Cloud

Data objects in Marketing Cloud consist of:

1. **[Data extensions](https://help.marketingcloud.com/en/documentation/exacttarget/subscribers/data_extensions_for_exacttarget_marketing_cloud/)** - are tables that can be used within the relational database in the Marketing Cloud account. Data in a data extension can either relate directly to the subscriber or contain information that is about a subscriber. Subscriber data extensions are sendable. Sendable data extensions contain a field that is mapped to the SubscriberKey. Data extensions contain fields which contain data.
2. **[Lists](https://help.marketingcloud.com/en/documentation/exacttarget/subscribers/lists)** - are data objects that contain subscriber data. All lists belong to the master All Subscribers list in the marketing Cloud account. Different lists are used to segment data. Examples of different lists might include newsletter, offers and a special announcements list. Lists that are public are included in the subscriber centre with the option to opt-in or out of that list. Optionally lists can have properties which are used to contain data about subscribers.
3. **[Publication lists](https://help.marketingcloud.com/en/documentation/exacttarget/subscribers/publication_lists/)** - are lists used with data extensions and the preference centre to manage if a subscriber is subscribed or unsubscribed. On an email send the publication list is used with the send. If the subscriber is not on the publication list then they are added. If the subscriber is already on the publication list and their status is subscribed then they are sent the email. If the subscriber's status is unsubscribed then they are not sent the email.
4. **[Suppressions lists](https://help.marketingcloud.com/en/documentation/exacttarget/subscribers/suppression_lists/)** - are lists used with data extensions to control if the subscriber will get sent an email. Suppression lists contain a list of email addresses that will not be sent an email. Think of a suppression list as a do not contact list. 

*Note*. Honor **Opt-out** requests promptly. You must process an unsubscribe request within 10 days, and your unsubscribe mechanism must be operational for at least 30 days after the mailing.

### Data extension data retention

Data extensions can use [data retention](https://help.marketingcloud.com/en/documentation/exacttarget/subscribers/data_extensions_for_exacttarget_marketing_cloud/managing_policies_for_a_data_extension/) to manage how data is retained or persisted within the Marketing Cloud account. Data retention options manage the period and what should occur when data is deleted. On delete either: individual records; all records; or all records and data extension are deleted.

### Data extension field types

Data extension field [data types](https://help.marketingcloud.com/en/documentation/exacttarget/subscribers/data_extensions_for_exacttarget_marketing_cloud/getting_started_with_data_extensions/data_types/) include:

* **Text** - contain text characters and have maximum length of 4,000 characters.
* **Number** - contain integer in the range of -2,147,483,648 to 2,147,483,648
* **Date** - contain dates. Various formats are accepted. Valid date values begin after 12/31/1772 and before 01/01/10000.
* **Boolean** - contain logical truth values. True values include: `1`; `Y`; `Yes`; or `TRUE`. False values include: `0`; `N`; `No`; or `FALSE`. 
* **Email** - contain an email address in a valid email format. An email field must exist for a data extension to be sendable.
* **Phone** - contain phone numbers in a valid phone format.
* **Decimal** - contain a number with a decimal point. When a decimal is defined length settings are used to define precision and scale.
* **Locale** - contain an ISO language and country code.

### Data extension creation options

Data extension creation options include: standard; filtered; and random data extensions. Standard data extensions contain fields used to store data. Filtered data extensions are generated by filtering fields from a sendable source data extension. Random data extensions contain randomly selected subscribers from a source data extension. Additionally data extensions can be created from data extension templates.

### How to retrieve data from the relational data model

[Queries](https://help.marketingcloud.com/en/documentation/exacttarget/interactions/activities/query_activity/) are used to select data into a target data extension. Queries use the SQL select statement. Queries can be used to overwrite, update or append the target data extension. When queries are used to update a data extension the target data extension must have a matching PrimaryKey to the query SQL select statement. SQL select statement support is based on SQL Server 2005 capabilities.

### When to use lists or data extensions.

Lists should be used where there are limited attributes requirements for up to 500,000 records. Use lists where import speed is not critical. Lists prefer simplicity over performance.

Data extensions should be used for where more than 500,000 subscriber records are required or where there are complex data relationships. Use a data extension if a flexible subscription model is preferred. Triggered sends and the SOAP/REST APIs require data extensions. Use data extensions where import speed is critical.

### How to import data into a list or data extension

The [import activity](https://help.marketingcloud.com/en/documentation/exacttarget/interactions/activities/import_activity/) can be used to import data into a list or data extension. Data can also be imported into a data extension using the SOAP/REST APIs.

## How emails are built with Salesforce Marketing Cloud

Required for an email send the following are required:

* Email content
* Recipients
* Publication list is optional
* Subject line
* Send from user name, classification or sender profile

Emails can be sent as a guided send or as a send activity in Automation Studio.

Emails can be personalised using:

* Personalisation strings
* AMPscript
* Dynamic content
* Guide Template Language

The difference between SSJS and AMPScript is that SSJS is processed by the Salesforce Marketing Cloud servers, SSJS is based on JavaScript and SSJS contains more features that AMPScript.

The difference between Dynamic Content and AMPScript is that Dynamic Content uses business rules with subscriber's attributes to display content areas, whereas AMPScipt uses lookup functions and logic statements to format content dynamically.

Other Marketing Cloud email add-on options include:

* Link Alias tags
* [Impression tracking](https://help.marketingcloud.com/en/documentation/exacttarget/tracking/impression_tracking/) - used to performance of emails that use regions with AMPscript or dynamic content.
* Web Analytics Connector - used to add params to all outgoing links

## How automation occurs with Salesforce Marketing Cloud

> Salesforce Marketing Cloud Automation Studio allows processes consisting of marketing activities to be triggered to start and be scheduled.

[Automation Studio](https://help.marketingcloud.com/en/documentation/automation_studio/) is a Marketing Cloud application that is used to manage multi-step processes. Automations in Automation Studio can be triggered by file changes or a schedule. Some of the automation activities include: 

* **Send email** - used to send emails.
* **Import file** - used to import a file into a data extension or list.
* **File transfer** - used to transfer a file from a specified location. The file transfer activity can also be used to unencrypt or uncompress.
* **Data extract** - used to create a file from a data extension.
* **SQL query** - used to run a SQL query.

An automation will generally be used to start a batch process to load a file or send a scheduled email.

In Automation Sudio triggered automations are used to start processes that import files and run subsequent tasks. Scheduled automations will generally be used to run recurring processes. Activities in a scheduled automation can be used to evaluate segments to determine if marketing activities should be run using queries and filtered data extensions.

## How contact builder is used with Salesforce Marketing Cloud

> Salesforce Marketing Cloud Contact Builder allows the data designer to access data, design data relationships and link data to external sources.

Contact Builder is a data design tool used access data contained in a Salesforce Marketing Cloud account and to design data relationships. 

### Examples for how to build attribute groups

#### Issue tracker example

In the issue tracker data relationship example, each contact record can have multiple issues. In this simple example, a contact record is linked to many records in the issues table.

##### How to implement in contact builder the issue tracker example

1. In data designer create a new attribute group.
2. Create or select the contacts data extension.
3. Link the contacts data extension to customer data object. The relationship between Customers Data and the contacts data extension should be a one-to-one relationship between the `Contact Key` field in the Customers Data object and the PrimaryKey in the contacts data extension.
4. Create or select the issues data extension.
5. Link the issues data extension to the contacts data extension. The relationship between the two data extensions should be a one-to-many relationship between the PrimaryKey on the contacts data extension and the corresponding field on the issues data extension.

### Contact Builder Tools

[Contact Builder](https://help.marketingcloud.com/en/documentation/contact_builder/) consists of the following tools:

* [**Data designer**](https://help.marketingcloud.com/en/documentation/contact_builder/data_designer/) - is used to create attribute groups which are used to organise data relationships. Data designer allows data extensions to be linked to contacts.
* [**All contacts**](https://help.marketingcloud.com/en/documentation/contact_builder/all_contacts/) - is used to list all contacts in the Marketing Cloud account. The population of contacts can be filtered on recently modified, source and channel. For each individual contact engagement, membership and attribute information is available.
* [**Data sources**](https://help.marketingcloud.com/en/documentation/contact_builder/data_sources/) - is used to describe where the Marketing Cloud account stores and locates contact attributes. There are three types of data source location consisting of system, synchronized and custom. System data sources are automatically allocated depending on functionality enabled in the Marketing Cloud. The synchronized data sources reflect how the Marketing Cloud account is using the Marketing Cloud Connector. Custom data sources is used to identify where the attributes for values originate.
* [**Data extensions**](https://help.marketingcloud.com/en/documentation/contact_builder/data_extensions/) - is used to create, read, update and delete data extensions. Data extensions are the tables used by the Marketing Cloud account to store data. Data extensions are used by the data design tool when organising relationships between objects.
* [**Imports**](https://help.marketingcloud.com/en/documentation/contact_builder/imports/) - is used to define an import definition.
* [**Contact**](https://help.marketingcloud.com/en/documentation/contact_builder/contacts_configuration/) - is used to determine channel send preferences. 

### Data Relationships

When relationships are created in the data design tool the cardinality for the relationship is specified, options include:

* **One-to-One relationship** - indicates that the data extensions relate to each other on a single primary key. 
* **Populations** - represent a master set of contacts with in a Marketing Cloud account. An example of using populations is a separate population for each patients, doctors and insurers in a health care provider Marketing Cloud account. Populations link to the contact model using the primary key with a one-to-one relationship. To avoid performance issues do not create more 3 populations in the data model.
* **One-to-Many relationship** - is where the primary key is linked to multiple items in another data extension. An example is a customer having multiple orders.
* **Many-to-Many Relationship** - is where there are multiple records in the linked data extensions that both contain the same value.

Changes to cardinality change the relationship that data extensions have with one another. After making changes to cardinality review all filtered lists, filters and scheduled sends.


## How Journey Builder is used with Salesforce Marketing Cloud

> Salesforce Marketing Cloud Journey Builder allows the campaign designer to implement and easily share complex digital marketing requirements. Journey Builder features an easy to use interface that does not require programming.

Journey Builder is a campaign planning tool that allows for the design and automation of responsive multi-channel campaigns that can be used to help guide customers through each step of their journey with the brand. The Salesforce Marketing Cloud Journey Builder user interface enables teams to easy understand how customer journey campaigns are executed. With this ease of use comes the ability for teams to apply an iterative design process where all parts of the campaign are tested. Gone is the campaign code only understood by programmers.

### Journey Builder Customer Scenarios

A campaigns in Journey Builder is described as an interaction. Journey Builder interactions are used to help manage the touch points that a customer has with a brand. To determine a customer touch points consider the sales funnel that a customer works through whilst purchasing.

#### 1 - Welcome and Nurturing Customer Journeys

Generally this is where the customer is working through recognition of problem, information search and evaluation of alternative products of the sales process. At this time the marketer will want to welcome the customer and differentiate their product. To enable this the marketer will develop a single view of the customer containing preference, segment and behavioral data that is used to communicate personalised and relevant information. The **welcome journey** represents a starting point in the relationship that the marketer will have with the customer. At this stage the customer will have signaled the marketer that they are interested in more information. The customer generally starts the welcome process by joining a membership program, completing a form or causing an update to a record in a CRM. After the customer has been welcomed **lead nurturing journeys** can be conducted to learn more about the customer and to help the customer move onto the purchasing stage.

#### 2 - Purchase and Offer Customer Journeys

At this point the marketer will want to help the customer make a purchasing decision. If the customer fails to complete the purchase then the marketer can direct the customer back to the lead nurturing customer journey. Offers can be included in content with welcome and lead nurturing customer journeys. Separate seasonal offers can be made to customer using journeys based on customer understandings.

#### 3 - Post-purchase Customer Journeys

Post-purchase Customer Journeys provides the marketer with opportunities to help the customer to make a repeat purchases.

### Steps to the set-up of a Salesforce Marketing Cloud Journey Builder Interaction

Before starting a Journey Builder interaction data must first be integrated into the Salesforce Marketing Cloud platform. Integration occurs when data is feed into a data extension. This can occur via the import activity, API or Salesforce connector. Contact builder is used to expose data for use with journey builder trigger events. Journey Builder then exposes activities available in the Salesforce Marketing Cloud.

1. **First define a campaign goal** - defining goals is important because they help to communicate campaign objectives and share progress.

2. **Next trigger an event to start the customer journey interaction** - this is done by configuring the interaction to listen for an event. Events include changes to data, date schedules and API requests.

3. **Configure the flow of activities** - in Journey Builder activities are described as a flow of send, wait, data update and custom activities. All decisions are  managed by rules that control how the contact progresses through the journey interaction.

### Journey Builder and Automation Studio Feature Comparison

Both Journey Builder and Automation Studio are campaign automation tools and as such have similarities which allow for the scheduling of activities to communicate with the customer. The main difference is that Journey Builder is a tool that works directly with the contact, whereas Automation Studio is designed to trigger processes that are batched against a collection of records. The following table provides a summary of differences between Journey Builder and Automation Studio.

|  | Journey Builder | Automation Studio |
| -------- | --------------- | ----------------- |
| Built in goal reporting | Yes | No |
| GUI includes: | Configuration and scheduling of activities and contact decision flow logic. | Configuration and scheduling of activities only. |  
| Processing method used to decision activities | In Journey Builder activities and decisions are applied at an individual contact level using the GUI. To decision if an activity should be performed a decision split is used and configured with an easy to use drag and drop filter method. | In Automation Studio activities are applied in a batch mode to all records. To decision if a subset of records should have an activity performed a query, filter and then send against the filter is performed. Queries and therefore filters are configured using SQL. |
| Trigger used to start processing | An event is fired at the data extension to determine if any contacts require processing activities. The fireevent is sent either from automation studio or the API. An API fire event may contain a payload of data that can be used to update the data extension used with the Journey Builder Interaction. | Automations can be triggered to start using a schedule, change of file on a watched location or API. The API used to start an Automation Studio automation is different to the one used with Journey Builder and cannot contain any payload of data.  |

### Journey Builder Links

> Visit [Journey Builder](https://www.salesforce.com/products/marketing-cloud/platform/digital-marketing-optimization/) for information about using Salesforce Marketing Cloud Journey Builder to create journeys across email, mobile, social, advertising and the web.

### Journey Builder Notes

* A contact in the Salesforce Marketing Cloud represents a person and includes all demographic and behavioral data associated to that person.
* Where event triggers depend on calculations and/or complex relationships data can be pre-processed using a query interaction. Where queries are used data is updated into the data extension (or table) associated with the Journey Builder Interaction. Depending on the requirement Contact Builder can also be used to manage complex data requirements.

