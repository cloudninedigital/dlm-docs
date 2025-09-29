---
sidebar_position: 2
---

# setting up user alert channels (in Settings)

Most of the settings are highover explained in the setting.md page, so this page will focus primarily on making sure you are able to set up alerting channels properly

## Email

Make sure email addresses are divided by a semicolon (simple as that). The email notification channel will hold the 'full' information about alerts, depending on the filtering in the settings on which kinds of issues to alert on. 

## Slack

The Slack notification channel will hold only new alerts, as a means to not overwhelm the user with all currently running issues. 

Get in contact with us, we have the slack notification set-up but have yet to streamline this process further. 

## Teams

The Teams notification channel will hold only new alerts, as a means to not overwhelm the user with all currently running issues. 

Go to (or create) a teams channel. Once in, go to 'Manage channel', and go to connectors and click 'Edit'. Open the 'Incoming Webhook' and set this up + click configure. create a name, potentially an image and click 'Create'. Once created, you can copy the webhook which should start with 'https://~yourworkspace~.webhook.office.com/etc'. 
