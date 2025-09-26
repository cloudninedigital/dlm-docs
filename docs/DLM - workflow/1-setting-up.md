---
sidebar_position: 1
---

# Setting up the Data Layer Monitor

Once you have secured your login to the Data Layer Monitor UI, the first step is to start tracking datalayer events, in order to start the validation process. The way in which we do that is by deploying a 'shadow pixel', a tag in your tag management system that gathers all pushed datalayer payloads with the relevant meta information. 

The overall setup follows these steps: 
- **Setup tag rule / template**: use one of the below snippets or templates to gather standard data layer formats, or device your own based on the logic. 
- **Fill in variables**: Fill in the relevant metadata variables like section
- **Determine firing trigger**: In best practice, we advise you to listen to all datalayer events coming in, but this is in practice fully customizable
- **test / deploy**: doublecheck if calls for every datalayer event are going out to https://collect.cloudninedigital.nl/<yourdomain>/datalayers/ 

### GTM dataLayer

To tap into the GTM dataLayer you can use the public workspace we've created. See the link https://github.com/cloudninedigital/int-shadow-pixel-gtm-template for a way to download the workspace and instructions on how to add this to your GTM environment.  

### Tealium utag.data datalayer

To setup the Data Layer Monitor shadowpixel for Tealium, use the below snippet as a base (filling in the <placeholders>)

```javascript
(function(){
    var dl = window.utag.data
    var dlb = b
// Create new filtered objects
    var dlmOutput = Object.fromEntries(
    Object.entries(dlb).filter(([key]) => !(key in dl))
    );
    function getBrowser(){
    var browser = "";
    if ((navigator.userAgent.indexOf("Opera") ||
    navigator.userAgent.indexOf('OPR')) != -1) { browser = 'Opera';
    }
    else if (navigator.userAgent.indexOf("Edg") != -1) { browser = 'Edge';
    }
    else if (navigator.userAgent.indexOf("Chrome") != -1) { browser = 'Chrome';
    }
    else if (navigator.userAgent.indexOf("Safari") != -1) { browser = 'Safari';
    }
    else if (navigator.userAgent.indexOf("Firefox") != -1) { browser = 'Firefox';
    }
    else if ((navigator.userAgent.indexOf("MSIE") != -1) || (!!document.documentMode == true)) { browser = 'IE';
    }
    else { browser ='unknown';
    }
    return browser };
    function getDeviceType () {
    var ua = navigator.userAgent;
    if (/(tablet|ipad|playbook|silk)|(android(?!.*mobi))/i.test(ua)) { return "tablet";
    }
    if ( /Mobile|iP(hone|od)|Android|BlackBerry|IEMobile|Kindle|Silk-Accelerated|(hpw|web)OS|Opera M(obi|ini)/.test( ua ) ) { return "mobile";
    }
    return "desktop";
    };
    var fetch_url = 'https://collect.cloudninedigital.nl/<your_client_id>/datalayers/?event=' + dl.tealium_event + "&domain=pvhb2b_<country>&section="+ <yourlogicforsection> + "&url=" + encodeURIComponent(window.location.toString().replace(window.location.search, "")) + "&device_type=" + getDeviceType() + "&browser=" + getBrowser() + "&datalayer_payload=" + encodeURIComponent(JSON.stringify(dlmOutput))
    fetch(fetch_url, { method: 'GET', }) .then(function(response){ response.json()}) })();
```

### custom setup

For the custom setup you can build up a call to the DLM shadowpixel yourself. 

```javascript
    //your logic to build up the datalayer payloads and custom parameters of the endpoint url


    //standard functions for determining browser and device type
    function getBrowser(){
    var browser = "";
    if ((navigator.userAgent.indexOf("Opera") ||
    navigator.userAgent.indexOf('OPR')) != -1) { browser = 'Opera';
    }
    else if (navigator.userAgent.indexOf("Edg") != -1) { browser = 'Edge';
    }
    else if (navigator.userAgent.indexOf("Chrome") != -1) { browser = 'Chrome';
    }
    else if (navigator.userAgent.indexOf("Safari") != -1) { browser = 'Safari';
    }
    else if (navigator.userAgent.indexOf("Firefox") != -1) { browser = 'Firefox';
    }
    else if ((navigator.userAgent.indexOf("MSIE") != -1) || (!!document.documentMode == true)) { browser = 'IE';
    }
    else { browser ='unknown';
    }
    return browser };
    function getDeviceType () {
    var ua = navigator.userAgent;
    if (/(tablet|ipad|playbook|silk)|(android(?!.*mobi))/i.test(ua)) { return "tablet";
    }
    if ( /Mobile|iP(hone|od)|Android|BlackBerry|IEMobile|Kindle|Silk-Accelerated|(hpw|web)OS|Opera M(obi|ini)/.test( ua ) ) { return "mobile";
    }
    return "desktop";
    };


// sending the request with the payloads (assuming these variables exist)
    var fetch_url = 'https://collect.cloudninedigital.nl/<your_client_id>/datalayers/?event=' + <yourlogictodeterminetheevent> + "&domain= + "<yourdomainname>+ "&section="+ <your logic for section> + "&url=" + encodeURIComponent(window.location.toString().replace(window.location.search, "")) + "&device_type=" + getDeviceType() + "&browser=" + getBrowser() + "&datalayer_payload=" + encodeURIComponent(JSON.stringify(<yourdatalayerpayload>))
    fetch(fetch_url, { method: 'GET', }) .then(function(response){ response.json()})

```




## Testing the setup

You can validate the setup in 2 ways: 
- **check in network tab**:  Open network tab in your browser to see if datalayer events trigger a call to https://collect.cloudninedigital.nl/<yourdomain>/datalayers/ with the correct outgoing payloads. 
- **check the DLM interface**: in the UI homepage you should be able to see the total number of events / per event type being measured, which could help you figure out if your shadowpixel setup is working


## next steps

When you've succesfully setup the shadowpixel, you can move on to the next step, which is datalayer configuration. 