---
sidebar_position: 3
---

# Live datalayer checker (Beta)

As part of fully integrating with the process of data collection, we have created a live checker functionality as part of the shadowpixel code setup. This is currently only available with GTM, please get in contact with us if you wish this to work in another environment as well. 

The main step to activate the functionality is to execute the following javascript in the console: 

```javascript
window.dlm.activate_live_checks();
```

From this point onwards every datalayer event you trigger in your session will be 'live-checked' and be reported on in your console, which can help you figure out mistakes in your setup more easily and faster whilst in development / debugging. 

Be aware that this feature is, as of yet, a beta product and might still be limited. 

