---
sidebar_position: 3
---

# Alert Detail Page

The Alert Detail component provides a comprehensive view of individual data layer alerts, allowing you to analyze, manage, and track issues in detail.

## Overview

The Alert Detail page displays detailed information about a specific alert, including:
- Alert metadata and description
- Statistical analysis
- Interactive visualizations
- Detailed breakdowns by various dimensions
- Failure combinations analysis

## Key Features

### Alert Management
- **Status Control**: Update alert status (Open, In Progress, Prioritized, Resolved, Closed)
- **Priority Management**: Set and modify alert priority (High, Medium, Low)
- **Ticket Linking**: Associate alerts with external ticket tracking systems

### Date Range Selection
- **Date From/To**: Select custom date ranges for analysis
- **Default Range**: Automatically loads last 7 days of data
- **URL Integration**: Date selections are reflected in the URL for easy sharing

### Statistical Overview
- **Total Occurrences**: Total number of times the event/parameter was measured
- **Failed Occurrences**: Number of times the issue occurred
- **Failure Rate**: Percentage of failures (Failed Occurrences/Total Occurrences)

### Interactive Charts
- **Failures Over Time**: Line chart showing failure trends
- **View Options**:
  - Daily view
  - Weekly view
- **Split Options**:
  - Split by Event
  - Split by Browser
  - Split by Device Type
  - Split by Section

### Dimension Analysis
Detailed breakdowns of failures by various dimensions:

#### Events
- List of events with failures
- Failure count and percentage per event

#### URLs
- List of URLs where failures occurred
- Clickable links to affected pages
- Failure count and percentage per URL

#### Browsers
- Browser-specific failure analysis
- Failure count and percentage per browser

#### Device Types
- Device type-specific failure analysis
- Failure count and percentage per device type

#### Sections
- Section-specific failure analysis
- Failure count and percentage per section

### Failure Combinations Table
Advanced table showing detailed breakdowns of failure combinations:

#### Column Management
- Toggle visibility of columns:
  - Event
  - Browser
  - Device Type
  - Section
  - URL
- Resizable columns
- Sortable by any column

#### Filtering Options
- Filter by:
  - Event
  - Browser
  - Device Type
  - Section
  - URL (text search)

#### Table Features
- **Sorting**: Click column headers to sort
- **Resizing**: Drag column edges to resize
- **Pagination**: Load more rows as needed
- **Failure Rate**: Calculated per combination

### Measured Values
- For "expected_values" type alerts:
  - Display of actual measured values
  - JSON formatting for easy reading

## Best Practices

1. **Regular Monitoring**: Check alert details regularly to track progress
2. **Status Updates**: Keep alert statuses current to reflect actual progress
3. **Priority Management**: Assign appropriate priorities based on impact
4. **Dimension Analysis**: Use the various breakdowns to identify patterns
5. **Chart Usage**: Utilize the interactive charts to spot trends
6. **Combination Analysis**: Use the failure combinations table to identify specific problematic scenarios

## Technical Notes

- **Data Loading**: 
  - Initial load includes last 7 days of data
  - URL data is loaded asynchronously for better performance
  - Caching is implemented to prevent unnecessary API calls

- **Performance Optimizations**:
  - Separate loading of URL and non-URL data
  - Pagination for large datasets
  - Efficient filtering and sorting

- **State Management**:
  - URL parameters for sharing and bookmarking
  - Persistent column widths
  - Remembered filter settings

- **Error Handling**:
  - Graceful error display
  - Loading states for better UX
  - Fallback displays when data is unavailable