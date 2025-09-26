---
sidebar_position: 2
---

# A guide to your first datalayer configuration

Configuration refers to the process of defining the desired state in which your datalayer and the pushed events operate. Without the definition of a desired state, there would be nothing to validate the incoming events. In practice, you will be defining each event that you expect to come in from your implementation, and all the parameters that are sent along with it. Furthermore, you will state the expected content of these incoming parameters wherever relevant.

## First base setup

As a full configuration can take some time to properly set up, you can start the configuration process in 2 ways:
- **from scratch**: define every single event and parameter yourself (potentially useful when a complete documentation is in place)
- **from your current datalayer implementation** : let the monitor define a first version of documentation based upon what is currently happening on your platform. Note: this does require you to have run the shadowpixel for at least a couple of days (also depending on your traffic levels). Go to Settings and choose to 'Re Run configuration Generation'. Be aware that if you already have a configuration in place, this will be overwritten with the new version. The generated configuration will, in most cases, not be the final form you’re looking for, as ‘what is currently happening’ may not reflect ‘what should be happening’. Most likely you’ll still need to add and delete events and parameters to your own preferences.

## Finetuning

Once a base of events and parameters is available, the next step is to finetune them to make sure specific alerts come up as relevant as possible.

### Events:
The event fine tuning is limited, but present:
* **Name**: the actual event key the validation will look for
* **Description (optional)**: an informative description, mostly relevant for documentation purposes (see documentation for more info)
* **Only alert from date (optional)**: relevant if an event is planned to be implemented, but not yet present. In this case you will want to generate documentation/ instructions for development, but don’t want the DLM to alert on the absence of the event just yet

### Event / Item parameters:
* **Name**: the actual parameter key the validation will look for. In the case of deeper level json data, you can shape the name of your parameter as ‘key.subkey.etc’. In the case of arrays you can use an ‘x’ instead of the index, so for example ‘ecommerce.items.x.price’.
* **Required**: whether or not the parameter is required to be measured.
* **JavaScript data type**: what the expected data type will be of the incoming parameter values
* **Allowed values (optional)**: a list of allowed values for this parameter. If a value is set that is outside of this list, an alert will follow.
* **Events**: in which events is the parameter expected to be present?
* **Matches Regex (optional)**: the alternative to allowed values, where you can state a regex pattern that the parameter value must follow.
* **Description (optional)**: an informative description, mostly relevant for documentation purposes (see documentation for more info)
* **Only alert from date (optional)**: relevant if a parameter is planned to be implemented, but not yet present. In this case you will want to generate documentation/ instructions for development, but don’t want the DLM to alert on the absence of the parameter just yet
* **Additional conditions (optional)**: A way to more granularly define in which situations the configuration for this parameter is relevant (see advanced use cases).
* **Additional conditions description (optional)**: an informative description of the additional conditions, will show up in documentation (see documentation for more info)
* **Always mark alerts on this field as "high-prio" (optional)**: if this fields is particularly critical to operations or marketing, you can make sure any alert related to this field will always be flagged as a high prio (see alerting for more info)

### **Example 1:** page.type

a datalayer payload that looks roughly like the below will be a common scenario for most websites:

```json
{"page": {"location": "example product page", "type": "pdp"}}
```

In this scenario, you could setup the page.type event parameter in the configuration like the below example:

* **Name**: page.type
* **Required**: true
* **JavaScript data type**: string
* **Allowed values**: ["home", "pdp", "plp", "checkout","content"] (because we have a finite amount of acceptable values that page.type can take)
* **Events**: ["page_view"]
* **Matches Regex (optional)**: (empty, because we already filled the allowed values)
* **Description (optional)**: the type of page being measured in our lovely website
* **Only alert from date (optional)**: (empty, because this is a live implementation)
* **Additional conditions (optional)**: (empty, not relevant here, we want the page.type to be measured everywhere)
* **Additional conditions description (optional)**: (empty)
* **Always mark alerts on this field as "high-prio" (optional)**: false

### **Example 2:** ecommerce.items.x.item_id

```json
{"page": {"location": "example product page", "type": "pdp"}, "ecommerce": {"items": [{"item_id": "12345", "item_variant": "asdda", "price": 20.21}]}}
```

In this scenario, you could setup the ecommerce.items.x.item_id item parameter in the configuration like the below example:

* **Name**: ecommerce.items.x.item_id
* **Required**: true
* **JavaScript data type**: string
* **Allowed values**: (empty, we're going to fill the Regex field)
* **Events**: ["view_item","add_to_cart", "begin_checkout", "purchase"]
* **Matches Regex (optional)**: ^\d{5,8}$ (a numeric string of between 5 to 8 digits)
* **Description (optional)**: the id of the item being interacted with
* **Only alert from date (optional)**: (empty, because this is a live implementation)
* **Additional conditions (optional)**: (empty, not relevant here, we want the ecommerce.items.x.item_id to be measured everywhere)
* **Additional conditions description (optional)**: (empty)
* **Always mark alerts on this field as "high-prio" (optional)**: false


## Advanced use-cases

### Additional Conditions - ecommerce.items.x.subscription_length_months

Let's say you are a company that sells both products and subscriptions, which are two separate funnels on your website. In one of the two funnels, the subscription_length is very uninteresting, because it is not applicable, in the other funnel it is actually quite important for your follow up analysis. This is where 'additional conditions' come in, to help you tighten further the logic on which to validate your incoming data. 

* **Name**: ecommerce.items.x.subscription_length_months
* **Required**: true
* **JavaScript data type**: number
* **Allowed values**: (empty, we're going to fill the Regex field)
* **Events**: ["add_to_cart", "begin_checkout", "purchase"]
* **Matches Regex (optional)**: ^\d{1,2}$ (a numeric string of between 1 to 2 digits)
* **Description (optional)**: the id of the item being interacted with
* **Only alert from date (optional)**: (empty, because this is a live implementation)
* **Additional conditions (optional)**: funnel_name equals 'subscription_funnel'
* **Additional conditions description (optional)**: Only relevant in subscription funnel
* **Always mark alerts on this field as "high-prio" (optional)**: false


## Rerunning scans

By default, the Datalayer Monitor validates the latest day of events on a daily basis, based upon the current configuration, and updates incrementally. If, however, you are actively in the process of changing the datalayer configuration, the new validation (and alerts) will only be using the new configuration from the new day of checking onwards only. 

This might mean that if you've changed a lot of configuration, you may 