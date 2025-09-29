---
sidebar_position: 4
---

# Using documentation for new features

Since a big part of the effort around the DLM is to define the accepted way of collecting data, we’ve made an effort to use this as a central source of documentation that can be used to document what is there, and help development with instructions how to properly track events.
The documentation section of the UI is directly fueled by the configuration, and shows, on event level, a mapping of parameters and their validations rules.

As an instruction purpose, this section shows how to properly implement this event with example collection calls (focused on various industry standards, SDK’s and TMS systems).

To add touch point meta information you have the room to upload screenshots of where events are being / should be triggered in the website, and you can add manual meta information about the event happening.

In the QA section you can see a list of recent issues found with the current event to make clear what still needs to be fixed.
As central documentation of data collection often occurs in the internal systems of companies, we provide a couple of integration options to keep documentation up to date in your target system:

* confluence sync
* Azure devops sync
* Markdown export

## confluence sync (Beta)
a periodical sync can be made with your confluence environment based on API connection, making sure documentation stays up to date periodically. In order to properly make this connection, setup the connection in the settings page. Below are instructions to setup the entire connection:

**Instructions to be made**

## Azure devops (Beta)

a periodical sync can be made with your azure devils environment based on API connection, which makes sure your documentation is kept up to date with recent events: In order to properly make this connection, setup the connection in the settings page. Below are instructions to setup the entire connection:

**Instructions to be made**

## Markdown export

If your documentation system is not featured within this overview, feel free to add a feature request to out backlog! In the meantime, though, you have the option to manually export markdown files and upload them to you system of choosing.