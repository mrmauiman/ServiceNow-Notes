# Assigning Tasks

### Steps to assign [[Tasks|tasks]]

1. Add **[[Role-Based Access#^6f1ab3|users]]** to **[[Role-Based Access#^86cca7|groups]]**
2. Add **[[Role-Based Access#^ea8475|roles]]** to **[[Role-Based Access#^86cca7|groups]]**
3. Assign **[[Tasks|tasks]]** to **[[Role-Based Access#^86cca7|groups]]**
4. Assign **[[Tasks|tasks]]** to **[[Role-Based Access#^6f1ab3|users]]**

## Assignment Rules
**Assignment Rules:** Used to automatically set a value in the **Assigned to** and/or **Assignment group** fields of a task record. ^fe17fa
- Location: **System Policy > Rules > Assignment** ^5d9d33

### Steps for creating an [[Assigning Tasks#^fe17fa|Assignment Rule]]
1. Navigate to the [[Assigning Tasks#^5d9d33|assignment module]] and select New
2. Complete Applies To tab
3. Complete Assign To tab
4. Test by createing an associated [[Tasks|task]] and verify it was assigned properly

### Assignment Rule Criteria
- The [[Tasks|Task]] record has been created (or modified) and then saved on a form.  For example, Createing an incident.
- The [[Tasks|Task]] record must be unassigned (no values in the **Assigned to** or **Assignment group** fields).
- The [[Assigning Tasks#^fe17fa| Assignment rule]] is the first rule that matches the specified table and conditions.  If more than one assignment rule matches the conditions, only the rule with the lowest **Order** value runs.

Assignment rules are also scriptable.

### Assignment Lookup Rules
**Assignment lookup rules:** are another type of assignment rule.  These rules only apply to **incident records**.  They have fewer options than other assignment rules that can be applied to any [[Tasks|task]].
- Location: **System Policy > Rules > Assignment Lookup Rules**.