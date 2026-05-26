---
sidebar_position: 2
---

# setting up user alert channels (in Settings)

Most of the settings are highover explained in the setting.md page, so this page will focus primarily on making sure you are able to set up alerting channels properly

## Email

Make sure email addresses are divided by a semicolon (simple as that). The email notification channel will hold the 'full' information about alerts, depending on the filtering in the settings on which kinds of issues to alert on. 

## Slack

The Slack notification channel will hold only new alerts, as a means to not overwhelm the user with all currently running issues. 

Step 1: Create a Slack App
Go to the Slack API Dashboard (https://api.slack.com/apps ) and click Create New App. Choose to create the app From scratch or From an app manifest. Name your app and select your workspace.

Step 2: Configure Permissions and ScopesNavigate to OAuth & Permissions in the left-hand sidebar. Scroll to the Scopes section and add the required bot token scopes:
* chat:write (Allows your app to send messages)
* channels:history / groups:history (If your app needs to read channel contexts)

Click Install to Workspace near the top of the page. Once authorized, you will receive a Bot User OAuth Token. 

Step 3: Add your bot to your channel by referencing them from the channel

Step 4: Add both the channel ID and the Oauth token in the settings section of the datalayer monitor. 

## Teams

The Teams notification channel will hold only new alerts, as a means to not overwhelm the user with all currently running issues. 

* Open Microsoft Teams and go to the channel where you want your notifications to appear.
* Click the three dots (...) next to your channel name and select Workflows (or go to Apps in the left sidebar and search for Workflows).
* Click the Create tab and search for the template titled "Post to a channel when a webhook request is received".
* Choose who can trigger the webhook (e.g., Anyone, Any user in my tenant, etc.) and select your specific Team and Channel.
* Click Create flow. Once saved, open the first trigger box ("When a Teams webhook request is received") to reveal and copy your unique HTTP POST URL.
* Add this URL to the teams webhook post in the settings page. 
