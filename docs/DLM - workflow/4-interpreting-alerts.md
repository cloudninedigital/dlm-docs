---
sidebar_position: 3
---

# Interpreting and acting upon alerts

Once you've got everything setup, your next step will be to interpret and act upon any alerts that might be inbound. The below section can help you navigating the incoming alerts. 

## Alert Definitions

The most up to date version will live in your settings section of the DLM, but here an overview of the definitions of each alert:

* **js_data_type** → Measured values for a certain parameter did not match the data type configured for that parameter. Example: parameter page_type is configured to expect a string, but has been measured as an integer.
* **required_fields** → A parameter was missing from a measured event, even though the parameter was expected to be measured for this event. Example: transaction_id was not measured in the purchase event, while the parameter was configured to be required in the purchase event.
* **unexpected_event** → An event was measured which was not configured. Example: event 'element_click' was measured a couple of times, even though it is not present in the current datalayer configuration.
* **unexpected_fields** → A parameter was measured for a certain event, even though it was not configured for this event. Example: parameter 'page_location' was measured a couple of times in the event 'page_view', while it was not configured at all, or not configured for the event 'page_view'.
* **unmeasured_event** → An event was not measured event though it was expected in the configuration. Example: event 'add_to_cart' was not measured at all yesterday, even though the configuration contains 'add_to_cart' as an event that is expected to be measured.
* **expected_pattern** → Certain values were measured for a parameter which did not match the configured regex pattern for that parameter. Example: the regex pattern for 'transaction_id' was set as '^\d8$', but suddenly the value 'asdas345' was measured for 'transaction_id'.
* **expected_values** → Certain values were measured for a parameter which were not in the list of allowed values. Example: the allowed values for 'page_type' were set to 'home', 'plp', 'pdp' and 'checkout', but suddenly the value 'inspiration' was measured for parameter 'page_type'.

## Main alert screen
In the main alert screen you can see basic information about the alerts taking place. here you can 
* see the short description of the alert
* split the alert occurences between the events in which it occured (split by events)
* Show measured values if the alert is related to specific values being set for a parameter
* dive deeper into granularity to watch the issue occurence over time

## Deep-dive into alerts

To further deep-dive into the issue at hand and find out in which situations the issue occurs, there's the alert detail page. You can get here by clicking on the 'View Details' button. Within this area, you will see a graphic display of the alert over the time period filtered on, and you can see a breakdown of the issue over the important meta-columns being measured in the DLM: 
* Browser
* Device type
* Section (assuming this is set-up correctly in the DLM shadowpixel)
* URL

### AI insights

If the above breakdown doesn't provide enough actionable insights to pinpoint where the issue is happening, the 'AI insights' portion of the alerts might. This section uses all other datalayer keys and values as input to search for a pattern in the issue that is occuring. 

an example here might be that an issue specifically always happens when the datalayer key 'login_status' is set to 'logged_in', or that the issue is particularly present when someone uses a specific payment provider in the checkout flow. This kind of information can be found by the AI insights portion of the detail view. 

This pattern recognition already could give you a headstart in pinpointing where (and in which development team) a fix should be implemented. 

## Acting upon alerts

When acting upon alerts, there's a couple of options to keep 'administration' of the issue up to date with current developments. 

* You can add a ticket link of the issue that has been generated in your own project tool (like Jira / Asana / etc.) to easily link the issue to any progress that has been made. 
* You can update the status from open to in progress or solved. This will make sure the alert doesn't show up in the alert email anymore, because it's clear it is being handled. 
* You can change the priority according to interpretation. An alert may be a lot lower priority in the context of your business than originally measured, or the other way around. You can manually override the priority of this alert to make the alert reflect the priority you deem it. 

## Process of re-configuration

Be aware that, at first hand, you might feel a bit overwhelmed with the amount of alerts coming in. You'll most likely enter a cyclic motion where alerts come in from the current state of datalayer configuration, that either result in actions to fix the datalayer, or an amendment to the current configuration (because sometimes edge cases are allowed in your setup that you simply hadn't thought of yet). 

Once the configuration is tight enough, you will enter a period of 'control', where the current known issues are being dealt with, and any new issue arising can easily be spotted and acted upon. 