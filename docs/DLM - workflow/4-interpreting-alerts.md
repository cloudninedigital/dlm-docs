---
sidebar_position: 3
---

# Interpreting and acting upon alerts

Once you've got everything setup, your 

## Alert Definitions

The most up to date version will live in your settings section of the DLM, but here an overview of the definitions of each alert:

* **js_data_type** → Measured values for a certain parameter did not match the data type configured for that parameter. Example: parameter page_type is configured to expect a string, but has been measured as an integer.
* **required_fields** → A parameter was missing from a measured event, even though the parameter was expected to be measured for this event. Example: transaction_id was not measured in the purchase event, while the parameter was configured to be required in the purchase event.
* **unexpected_event** → An event was measured which was not configured. Example: event 'element_click' was measured a couple of times, even though it is not present in the current datalayer configuration.
* **unexpected_fields** → A parameter was measured for a certain event, even though it was not configured for this event. Example: parameter 'page_location' was measured a couple of times in the event 'page_view', while it was not configured at all, or not configured for the event 'page_view'.
* **unmeasured_event** → An event was not measured event though it was expected in the configuration. Example: event 'add_to_cart' was not measured at all yesterday, even though the configuration contains 'add_to_cart' as an event that is expected to be measured.
* **expected_pattern** → Certain values were measured for a parameter which did not match the configured regex pattern for that parameter. Example: the regex pattern for 'transaction_id' was set as '^\d8$', but suddenly the value 'asdas345' was measured for 'transaction_id'.
* **expected_values** → Certain values were measured for a parameter which were not in the list of allowed values. Example: the allowed values for 'page_type' were set to 'home', 'plp', 'pdp' and 'checkout', but suddenly the value 'inspiration' was measured for parameter 'page_type'.

## main alert screen


## Deep-dive into alerts



## Acting upon alerts


## Process of re-configuration

In practice, you'll most likely see a cyclic motion happening where alerts come in from the current state of datalayer configuration, that either result in actions to fix the datalayer, or an amendment to the current configuration (because sometimes edge cases are allowed in your setup that you simply hadn't thought of yet). 