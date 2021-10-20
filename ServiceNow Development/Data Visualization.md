# Data Visualization
Visualizations convey complex data, which can be difficult to describe in words using a chart or graph.  Application developers visualize data to trasnform records into meaningful information for the application's users.  The information should drive actions.

## Data Visualization Options
The Now Platform's visualizations are:
- **Real time:** always show current information
- **Secure:** users can only see data that they are authorized to see
- **Native:** easily used throughout the [[Now Platform|Now Platform]]

Data visualizations allow developers to present data to users in easily consumable ways.  The formats are:
- **Reports:** visualization of data for analysis
- **On-demand bar and pie charts created from lists:** users create charts for any column on a list
- **% Complete indicaters in lists:** bar indicates how close a record is to completion
- **Chart data type for forms:** inserts a report into a form
- **Dashboard:** collection of widgets consisting of reports and analytics

## Reports
**Reports** organize, suimmarize, and present data to convey information in a meaningful way.  Developers create reports for applications for many reasons, including:
- Identifying trends
- Monitoring field values
- Looking for outlying data
- Tracking work
- Viewing progress

These are the report types:
![[ReportTypes.png]]
![[ReportTypes2.png]]

### Choosing a Report Type
The goal of a report is to convey meaningful information to the report consumer.  Select report type which conveys the required information in an actionable way.  For example, if the goal is to identify a trend over time, a pie chart is probably not the best choice.  If the goal is to identify the current state, a pie chart might be the perfect choice.

### View/Run Reports
To view or run a report, navigate to **Reports > View / Run**.

If a user is authorized to create reports and has not created a report, the *My Reports* tab prompts the user to create a report.

### Report Designer
**Report Designer** is ServiceNow's user interface for creating and editing reports.  Users with a report or admin role can edit and save reports.  

#### Report Roles
The report roles are:
- **report_admin:** manage reports
- **report_global:** create global reports
- **report_group:** create reports belonging to a group the user is a member of
- **report_publisher:** make reports available on a public page
- **report_scheduler:** schedule reports to be delivered by email
- **report_user:** create reports and view reports shared with the user

In addition to report roles, developers must have the right permissions to access the data for their reports.

#### Report Designer Tabs
Report Designer has four tabs:
- **Data:** data source for the report
- **Type:** visulaization of the report such as bar, pie, or histogram
- **Configure:** report configuration which is dependent on report type
- **Style:** report appearence

##### Data
Use the data tab to configure the report name and where the data comes from.

- **Report name:** Specify the title of the report.
- **Source type:** Choose *Table* or *Data source*.  If the MetricBase plugin is enabled, there is an additional data type option of *MetricBase*.
- **Table:** If the *Source type* is *Table* or *MetricBase*, select the table for the report.  All records from the table are included.
- **Data Source:** If the *Source type* is *Data source*, select the source for the data.

Data sources are filtered sets of table data.  Use the **Reports > Administration > Report Sources** module to create new data sources.

##### Type
Choose a report type by clicking a thumbnail.  The report types are organized by groups.

##### Configure
The options on the *Configure* tab are dependent on the selected report type.  The ServiceNow docs site explains the *Configure* tab options.  Click [Creating reports](https://docs.servicenow.com/bundle/rome-performance-analytics-and-reporting/page/use/reporting/reference/report-types-creation-details-rd.html) and select a *report type* to see the options.

##### Style
The options on the *Style* tab are dependent on the selected report type.  The *Style* tab contains additional tabs which may include:
- General
- Title
- Legend
- Axis

The ServiceNow docs site explains the *Style* tab options.  Click [Creating Reports](https://docs.servicenow.com/bundle/rome-performance-analytics-and-reporting/page/use/reporting/reference/report-types-creation-details-rd.html) and select a *report type* to see the options.

##### Running and Saving
After configuring a report, Click the **Run** button to run the report without saving the changes.  To run the report and save the changes, click the **Save** button.