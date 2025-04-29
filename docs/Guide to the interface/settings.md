---
sidebar_position: 6
---

# Settings

The Settings component provides a comprehensive interface for managing your data layer monitoring system. It includes settings for alerts, notifications, user management, and system definitions.

## Overview

The Settings interface consists of three main sections:
1. **Settings**: Alert configurations and thresholds
2. **Definitions List**: Priority and alert type definitions
3. **User Management**: User administration and access control

## Features

### Settings

#### Alert Switches
Toggle switches for different alert conditions:
- **Alert only on new issues**: Only trigger alerts for newly detected issues
- **Alert on high-prio issues**: Enable alerts for high priority issues
- **Alert on medium-prio issues**: Enable alerts for medium priority issues
- **Alert on low-prio issues**: Enable alerts for low priority issues
- **Send Notification on 'no new' issues**: Notify when no new issues are found

#### Alert Thresholds
Configure percentage thresholds for issue prioritization:
- **Medium issue alert percentage**: Threshold for medium priority issues
- **High issue alert percentage**: Threshold for high priority issues
- **Note**: High threshold must be greater than medium threshold

#### Alert Notifications
Configure notification channels:

##### Email Notifications
- **Email Addresses**: Semicolon-separated list of email addresses
- **Format**: `email1@domain.com;email2@domain.com`

##### Slack Notifications
- **Channel Configuration**:
  - Channel ID
  - API Token
- **Multiple Channels**: Add/remove channels as needed

##### Teams Notifications
- **Webhook Configuration**:
  - Webhook URL
- **Multiple Channels**: Add/remove channels as needed

#### System Maintenance
- **Re Run Scan**: Trigger a new scan from a specific date
- **Re Run Configuration Generation**: Regenerate system configuration

### Definitions List

#### Priority Definitions
Clear explanations of issue priority levels:

##### Low Priority
- Unexpected events/parameters
- Incorrect JavaScript types
- Issues occurring in ≤ medium threshold percentage

##### Medium Priority
- Required fields not measured
- Values outside expected range
- Issues occurring between medium and high thresholds

##### High Priority
- Required fields not measured
- Values outside expected range
- Expected events not measured
- Custom high-priority configurations

#### Alert Definitions
Detailed explanations of alert types:

##### Data Type Alerts
- **js_data_type**: Mismatched JavaScript data types
- Example: String expected, number received

##### Field Alerts
- **required_fields**: Missing required parameters
- **unexpected_fields**: Unexpected parameters present
- **expected_pattern**: Pattern mismatch
- **expected_values**: Value not in allowed list

##### Event Alerts
- **unexpected_event**: Unconfigured event detected
- **unmeasured_event**: Expected event not measured

### User Management

#### User Administration
- **Add Users**: Create new user accounts
- **Edit Users**: Modify existing user settings
- **View Users**: List all system users

#### User Properties
- **Username**: Unique identifier
- **Email**: Contact information
- **Full Name**: User's complete name
- **Role**: Access level (viewer/editor/admin)
- **Invite Status**: Pending/activated

#### Role Types
- **Viewer**: Read-only access
- **Editor**: Can modify configurations
- **Admin**: Full system access

## Usage

### Configuring Alerts
1. Navigate to Settings tab
2. Configure alert switches
3. Set alert thresholds
4. Add notification channels
5. Save changes

### Managing Users
1. Navigate to User Management tab
2. Add new users or edit existing ones
3. Set appropriate roles
4. Monitor invite status

### Understanding Definitions
1. Navigate to Definitions List tab
2. Review priority definitions
3. Understand alert types
4. Reference for issue classification

## Best Practices

### Alert Configuration
1. **Threshold Setting**:
   - Set realistic thresholds
   - Consider data volume
   - Monitor alert frequency

2. **Notification Channels**:
   - Use multiple channels
   - Verify channel configurations
   - Test notifications

3. **Alert Switches**:
   - Enable only necessary alerts
   - Consider team capacity
   - Monitor alert volume

### User Management
1. **Role Assignment**:
   - Follow least privilege principle
   - Regular role review
   - Document access changes

2. **User Creation**:
   - Verify email addresses
   - Set appropriate roles
   - Monitor activation status

3. **Security**:
   - Regular access review
   - Secure credentials
   - Monitor user activity

## Technical Notes

### Data Management
- **Configuration Storage**: Secure storage of settings
- **User Data**: Encrypted storage
- **API Tokens**: Secure handling

### Performance
- **Caching**: Efficient data loading
- **Updates**: Batch processing
- **Validation**: Real-time checks

### Security
- **Access Control**: Role-based access
- **Authentication**: Secure login
- **Authorization**: Permission checks

## Troubleshooting

### Common Issues
1. **Alert Configuration**:
   - Verify channel settings
   - Check API tokens
   - Validate email addresses

2. **User Management**:
   - Check invite status
   - Verify role permissions
   - Review access logs

3. **System Maintenance**:
   - Monitor scan progress
   - Check configuration generation
   - Review error logs

### Getting Help
- Check system logs
- Review documentation
- Contact support

## Maintenance

### Regular Tasks
1. **User Review**:
   - Audit user access
   - Update roles
   - Remove inactive users

2. **Alert Review**:
   - Check threshold effectiveness
   - Update notification channels
   - Monitor alert volume

3. **System Updates**:
   - Regular configuration generation
   - System scans
   - Performance monitoring
