# Triggers
**Triggers:** starts a flow when the conditions of the trigger are met.  Triggers can be **Record-Based**, **Schedule-Based**, or **Application-Based**.

**Record-Based:** Runs a flow after a record has been created, updated, or deleted.  When using a Record-Based trigger, the triggering record can be used later in the flow as input for actions.

**Schedule-Based:** Runs a flow at a specified date and time: daily, weekly, monthly, etc.  The execution time can be used as an input for actions in the flow.

**Application-Based:** Added when the associated application spoke is activated.  For example, these types of triggers allow you to trigger a flow when an item is requested from the service catalog.  In the same instances, a plug-in might need to be activated as well.

**Spoke:** Contains [[Flow Designer|Flow Designer]] triggers and actions dedicated to a particular application.  For example, the ITSM Spoke actions for managing Task records such as the Create Task action.  Spokes are activated when their parent application is activated. ^Spoke