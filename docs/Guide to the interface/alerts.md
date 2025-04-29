---
sidebar_position: 2
---

# Alerts

Detailed view of data layer issues and alerts with advanced filtering and sorting capabilities

# Dashboard Table

The dashboard table provides a detailed view of all data layer issues and alerts, allowing you to filter, sort, and analyze the data in depth.

## Table Overview

The table displays comprehensive information about each alert, including:

### Core Information
- **Details**: Link to view detailed information about the alert
- **Status**: Current status of the alert (Open, Prioritized, In Progress)
- **Priority**: Alert priority level (High, Medium, Low)
- **Date**: When the alert was reported
- **Type**: Whether it's an event or parameter issue
- **Name**: The name of the affected event or parameter
- **Alert Type**: The specific type of alert
- **Alert Description**: Detailed description of the issue

### Additional Information (Optional)
- **Event**: Shows the specific event when split by event is enabled
- **Measured Values**: Displays the actual values measured when show measured values is enabled
- **Browser**: Browser information in detailed report mode
- **Device Type**: Device type information in detailed report mode
- **Section**: Section information in detailed report mode
- **URL**: URL information in detailed report mode
- **Failed Occurrences**: Number of times the issue occurred
- **Total Occurrences**: Total number of times the event/parameter was measured
- **Failure Rate**: Percentage of failures (Failed Occurrences/Total Occurrences)

## Filtering Options

The table provides extensive filtering capabilities:

### Date Filters
- **Date From**: Start date for the data range
- **Date To**: End date for the data range

### Alert Filters
- **Alert Type**: Filter by specific alert types
- **Parameter/Event Name**: Filter by specific parameters or events
- **Granularity**: Choose between all_time, date, week, or month views
- **Split by Event**: Enable to show event-specific information
- **Show Measured Values**: Enable to display actual measured values
- **Exclude Not-Yet-Valid Alerts**: Filter out alerts that haven't reached their validity date
- **Only Show 'New' Alerts**: Filter to show only new alerts
- **Alert Priority**: Filter by priority level (High, Medium, Low)
- **Status**: Filter by alert status (Open, Prioritized, In Progress)

### Detailed Report Options
- **Detailed Report Columns**: Choose which additional columns to display (browser, device_type, section, url)

## Sorting Capabilities

The table supports sorting by multiple columns:
- Status
- Priority
- Date
- Name
- Alert Type
- Browser (in detailed mode)
- Device Type (in detailed mode)
- Section (in detailed mode)
- URL (in detailed mode)
- Failed Occurrences
- Failure Rate

## Interactive Features

### Alert Management
- **Status Updates**: Change the status of alerts directly from the table
- **Priority Updates**: Modify alert priorities as needed
- **Configuration Links**: Click on parameter names to view their configuration

### Data Export
- **Excel Export**: Export the current table view to Excel for further analysis

### Pagination
- **Load More**: Load additional rows when available
- **Default View**: Initially shows 20 rows

## Best Practices

1. **Regular Review**: Check the table regularly to identify and address issues
2. **Filter Usage**: Use filters to focus on specific types of issues or time periods
3. **Status Management**: Keep alert statuses up to date to track progress
4. **Priority Assignment**: Assign appropriate priorities to ensure critical issues are addressed first
5. **Data Export**: Use the Excel export feature for detailed analysis or reporting
6. **Configuration Review**: Use the configuration links to verify and update parameter settings

## Technical Notes

- The table automatically loads data for the last 7 days by default
- Status changes are automatically saved and persist for 30 days
- The table supports real-time updates as new data comes in
- All filters can be combined to create specific views of the data
- The table maintains state between page refreshes using URL parameters