# Scheduled Script Executions (SSE)
**Sceduled Script Executions:** Also known as Jobs, are automated server-side script logic that executes at a specific time on a recurring basis.

Should be used when applications processes require script logic to be executed based on a time schedule.  For example:
- Periodically query a database table
	- Find records with overdue Due dates
	- Find records with Due dates in the near future
	- Locate all requests from a particular user
	- Look for records that have been in a certain state, such as resolved, too long
- Update records
	- Set the State field value to Closed Complete after a fixed time has elapsed
	- Assign unassigned records to a user
	- Delete to re-assign all records created by a user

## Creating a Scheduled Script Execution
1. Click the **Create Application File** link
2. Choose the **Scheduled Script Execution** file type
3. Configure the new file

## SSE Scripts
Schedule Script Execution scripts run server-side and therefore use the server-side API.  Unless an administrator clicks the **Execute Now** button, SSEs are not triggered by user interactions.  SSEs are not associated with records and have no access to the previous of current objects used by many other server-side script types.

SSEs have two scripting fields:
- Condition
- Run this script

### Condition Script
Select the *Conditional* option to open the *Condition* script field.  Use the *Condition* script to write server-side logic to determine if the script in the *Run this script* field should execute.  The *Condition* script must set the *answer* variable to *true* for the *Run this script* field's script to execute.

The *Condition* script shown tests whether today is a weekday of a weekend.  The script returns true only for weekdays.

```js
// Create the answer variable
var answer = true;

// Get today's date and determine which day of the week it is
var rightNow = new GlideDateTime();
var dayOfWeek = rightNow.getDayOfWeekLocalTime();

// If today is Saturday(6) or Sunday(7), set the answer variable to false
// so the "Run this script" field's script does not execute.
if(dayOfWeek == 6 || dayOfWeek == 7) {
	answer = false;
}

// End script with something that resolves to true or false
answer;
```

Use a *Condition* script to seperate the conditional logic and prevent having to nest code serveral layers deep.

Variables declared in the *Condition* script are known to the *Run this script* field if permitted by the rules of JavaScript Scope.

If there is no *Condition* script, the field returns true.

### Run This Script
The server-side script logic in the *Run this script* field executes when the Scheduled Job is triggered and the *Condition* script returns *true*.

The script shown querries the database for Occasion records that match today's month and day and logs the record numbers in the Application Log(**System Logs > System Log > Application Logs**).

```js
// Get today's month and day to compare with occasions
var month = rightNow.getMonthLocalTime();
var day = rightNow.getDayOfMonthLocalTime();

// Occasion records have a month and a day field.
// Query the database for Occasion records that match
// today's month and day.
occToday.addQuery('occasion_month', '=', month);
occToday.addQuery('occasion_day', '=', day);
occToday.query();

// Write a log message for each Employee celebrating an occasion
while(occToday.next()) {
	gs.info("Occasion record: " + occToday.number);
}
```

Notice that the variable rightNow used in lines 2 and 3 of the script is not defined in the *Run this script* field.  The rightNow variable was create in the *Condition* field script.

### Testing Scripts
To test an SSE, the developer could wait until the next scheduled execution to see if the script worked.  This is not ideal as it would lead to a long development cycle, especially if a script trun anually or even just monthly.  A better option is to use the **Execute Now** button.  The button is available only after saving an SSE script.

**On Demand** SSEs only run if the administrator presses the *Execute Now* button.

## Checking the Schedule
To see the SSEs on the schedule for today, navigate to **System Scheduler > Scheduled Jobs > Today's Scheduled Jobs**.