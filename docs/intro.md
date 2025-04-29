---
sidebar_position: 1
---

# Getting Started

The Data Layer Monitor is a powerful tool designed to safeguard the integrity of your web analytics implementation. By continuously validating your data layer across key events and parameters, it ensures your tracking setup remains consistent and reliable.

## Core Functionality

-   **Data Layer Validation**
    The tool verifies that the correct data is being pushed into the data layer at crucial moments. It ensures that both event names and parameter values match your expected configuration.

-   **State Comparison**
    Every check compares the current state of the data layer against the desired state, identifying any mismatches or missing values.

-   **Configuration-Based Setup**
    The desired state is defined through a configuration interface within the tool. This setup doubles as live documentation of your tracking plan, making it easy to manage, review, and update over time.

## Error Categorization

Errors are flagged with one of three severity levels:

-   **High:** Critical issues likely to break reporting or attribution, like purchase event not being measured in more than 5% of the cases.
-   **Medium:** Important discrepancies that could impact analysis, like item brand parameter missing in 2% of the add to cart events.
-   **Low:** Minor issues, such as unexpected events measured or wrong data type.

## Notifications & Reporting

-   Automated error reports are sent daily every morning.
-   You can choose your preferred notification channel: Slack, Microsoft Teams, or Email.
-   Reports highlight affected pages, events, and specific parameter issues, giving your team a clear path to resolution.

## Frequently Asked Questions

**Q: What platforms does the Data Layer Monitor support?**

A: The tool is platform-agnostic and works with any site that implements a structured data layer, including setups using Google Tag Manager, Tealium, or custom solutions.

**Q: How is the “desired state” of the data layer defined?**

A: The desired state is configured in the Data Layer Monitor interface. It acts as both the configuration and documentation of your ideal data layer setup — specifying expected events, parameters, and values.

**Q: How often are checks performed?**

A: Data layer checks are run continuously in the background, and any issues found are compiled into a daily report sent out every morning.

**Q: How do I receive alerts?**

A: You can choose your preferred communication channel: Slack, Microsoft Teams, or Email. You can also configure which teams or individuals receive which types of errors.

**Q: Can I prioritize or ignore certain events?**

A: Yes — the configuration allows you to assign severity levels to specific parameters or events, and you can mark non-critical fields as optional to reduce noise in reporting.