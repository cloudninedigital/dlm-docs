---
sidebar_position: 1
---

# Home

Monitor your data layer health and track issues in real-time

# Dashboard Overview

The dashboard provides a comprehensive overview of your data layer's health and performance. It consists of three main sections:

## Monitor Health

This section displays three key metrics that help you assess the overall health of your data layer:

### Data Up Time
- **Description**: Percentage of hours in which any data was measured
- **Color Coding**:
  - 🟢 Green: 100% uptime
  - 🟠 Orange: Less than 100% but more than 48 hours
  - 🔴 Red: Less than 48 hours

### Event Availability
- **Description**: Percentage of configured events that were actually measured
- **Color Coding**:
  - 🟢 Green: 100% availability
  - 🟠 Orange: Between 50% and 100%
  - 🔴 Red: Less than 50%

### Data Quality
- **Description**: Percentage of verified data points out of total checked data points
- **Color Coding**:
  - 🟢 Green: 90% or higher
  - 🟠 Orange: Between 50% and 90%
  - 🔴 Red: Less than 50%

## Issues Overview

This section provides a summary of issues reported in the last 7 days (excluding today), categorized by priority:

### High Priority Issues
- **New Issues**: Shows the number of new high-priority issues that require immediate attention
- **Total Issues**: Displays the total number of high-priority issues with a comparison to the previous 7 days
- **Definition**: Events or parameters that aren't measured while expected, or parameters that measure values outside of allowed values. Issues are considered high priority if they occur in more than 5% of instances or if the field is marked as 'high priority alert field'

### Medium Priority Issues
- **Total Issues**: Shows the total number of medium-priority issues with a comparison to the previous 7 days
- **Definition**: Issues worth looking into on short notice, occurring in less than 5% of instances

### Low Priority Issues
- **Total Issues**: Displays the total number of low-priority issues with a comparison to the previous 7 days
- **Definition**: Issues that clutter your data collection but don't cause immediate breakage (e.g., unexpected events or parameters being measured, or parameters with unexpected JavaScript types)

## New Alerts Table

The alerts table provides detailed information about recent issues:

### Table Columns
- **Date**: When the alert was reported
- **Alert Type**: The type of issue detected
- **Priority**: Issue priority level (High/Medium/Low)
- **Mismatches**: Number of mismatches detected
- **Total Occurrences**: Total number of times the issue occurred
- **Failure Rate**: Percentage of failures (mismatches/total occurrences)

### Alert Types
- **Expected Values**: Values set for a field that were not in the list of expected values
- **JavaScript Data Type**: Field did not match the expected JavaScript data type
- **Required Fields**: Field was not measured even though it was expected
- **Unexpected Fields**: Field was measured while it was not expected
- **Unexpected Event**: Event was measured while it was not expected
- **Unmeasured Event**: Event was not measured even though it was expected
- **Expected Pattern**: Field did not match the expected pattern

## Navigation

- Click on any metric or issue count to navigate to the detailed table view with relevant filters applied
- Use the table headers to sort the alerts by different criteria
- Hover over the help icons (🛈) to see detailed explanations of each metric

## Best Practices

1. **Regular Monitoring**: Check the dashboard daily to identify and address issues promptly
2. **Priority Management**: Focus on high-priority issues first, as they indicate critical problems
3. **Trend Analysis**: Use the comparison with previous periods to identify improving or worsening trends
4. **Data Quality**: Aim to maintain data quality above 90% for optimal performance