# Notifications
## Outbound Emails
Notifications send outbound email to one or more recipients in response to specific activities in ServiceNow.  Notifications can be sent when:
- Records are inserted or updated
- Events are generated
- The *Notification* activity executes in a workflow
- The *Send Email* action executes in a flow

## Creating Notifications
1. Select the **Create Application File** link
2. Choose the **Notification** file type
3. Configure the new file

There are three sections to configure in a Notification
- When to send
- Who will receive
- What it will contain

## Notification Email Scripts
Use Notification Email Scripts to print Notification message content from a server-side script.  Although Notification Email Scripts are application files, they must be created in the main ServiceNow browser window and not in Studio.  Found at **System Notification > Email > Notification Email Scripts**.

The scripts have access to:
- current (GlideRecord API)
- email (GlideEmailOutbound API)
- template (TemplatePrinter API)
- event (only for notifications responding to events)

This sample script uses the *current* and *template* objects
```js
(function runMailScript(current, template, email, email_action, event) {

	// Construct a GlideRecord query to find all birthdays with a matching month
	// and day as the current occasion
	
	var sameBirthday = new GlideRecord('x_snc_employee_spe_occasions');
	sameBirthday.addQuery('occasion_month', current.occasion_month);
	sameBirthday.addQuery('occasion_day, current.occasion_day');
	sameBirthday.addQuery('u_occasion', 'birthday');
	
	sameBirthday.query();
	
	// Print to the Message field on a notification
	template.print(sameBirthday.getRowCount() - 1 + " employees in the company share your birthday.");
	
})(current, template, email, email_action, event)
```

### Using a Notification Email Script in a Message
Include a Notification Email script in a notification *Message HTML* field using this syntax: **_${mail_script:\<scriptName\>}_**