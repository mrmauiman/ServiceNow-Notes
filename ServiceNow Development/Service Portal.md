# Service Portal
A portal is a ServiceNow UI, built using the Service Portal framework, which provides an alternative user experience to the standard UI.  It is an intuitive way for users to interact with the underlying Now Platform using a minimum number of clicks from any device: desktop, tablet, or smartphone.  Portals allow users to access any platform component including:
- Selected records from important tables, such as all tasks assigned to the user
- Metrics, reports, and analytics
- Service Catalog
- Knowledge Base
- Surveys
- User Profiles
- Approvals
- And More!

A portal is easily branded and themed to match your organization's branding.

## Portal Anatomy
Users access a portal using a URL or module

ServiceNow administrators can configure a portal to be a user's landing page when they log in to ServiceNow

### Pages
Each portal is made up of one or more pages.  Pages are not unique to a portal and can be used in as many portals as needed.  A portal applies themeing, a header, a footer, and som additional metadata to a page, allowing reuse without changes to a page's definition.

### Containers
Portal pages are organized by containers.  Containers create the page layout by organizing pages into sections.  Containers are divided into rows.  Containers typically contain a single row but can have multiple rows.   Each row can contain a different number of columns.

### Widgets
Widgets define the content for a portal.  The default portal container is one row which contains three columns.  Each column can contain any number of widgets.

## Service Portal Framework
The Service Portal Framework is a set of tools, APIs, AngularJS services and directives, and componets used to create portals.  The Service Portal Framework helps developers and non-technical administrators create attractive and engaging user experiences which drive employee adoption of critical enterprise applications.

### Service Portal Configuration
To access the Service Portal framework tools, navigate to **Service Portal > Service Portal Configuration**.  The Service Portal configuration page opens in a new tab and contains:
- **Branding Editor:** Apply your company's branding to the portal including logo, background, and color scheme.
- **Designer:** Create page layouts by adding or modifying containers, rows, columns, and widgets.
- **Page Editor:** Use a hierarchical map to view or edit page elements.
- **Widget Editor:** Create or edit widgets.
- **New Portal:** Create a Service Portal.
- **Get Help:** View the Service Portal documentation on docs.servicenow.com