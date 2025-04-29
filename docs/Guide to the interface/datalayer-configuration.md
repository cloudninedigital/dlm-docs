---
sidebar_position: 4
---

# Datalayer Configuration

The Configuration Environment is the central hub for managing your data layer implementation. It allows you to define events, parameters, and validation rules that ensure your data layer is properly structured and validated.

## Getting Started

### Accessing the Configuration
1. Navigate to the Configuration page in your dashboard
2. You'll see three main tabs at the top:
   - Events
   - Event Parameters
   - Item Parameters

### Basic Navigation
- Use the tabs to switch between different configuration types
- Each section has its own table view with expandable rows
- Click the arrow (▶) next to any entry to view/edit its details
- Use the search and filter options at the top to find specific entries

## Understanding the Sections

### Events
Events are the core building blocks of your data layer. They represent specific user actions or system events that you want to track.

#### Creating a New Event
1. Click "Add new entry" at the top of the Events section
2. Fill in the required fields:
   - **Name**: A unique identifier for your event (e.g., "purchase", "add_to_cart")
   - **Description**: A clear description of what the event represents
   - **Event Parameters**: Select which parameters should be associated with this event
   - **Alert From Date**: Set when alerts for this event should start being generated

#### Example Event Configuration
```json
{
  "name": "purchase",
  "description": "Triggered when a user completes a purchase",
  "event_parameters": ["transaction_id", "value", "currency", "items"],
  "alert_from_date": "2024-01-01"
}
```

### Event Parameters
Event parameters are the data points collected with each event. They define what information should be captured and how it should be validated.

#### Creating a New Event Parameter
1. Click "Add new entry" in the Event Parameters section
2. Configure the following:
   - **Name**: Parameter identifier (e.g., "transaction_id")
   - **Data Type**: The expected data type (string, number, etc.)
   - **Required**: Whether this parameter must be present
   - **Allowed Values**: Specific values that are acceptable
   - **Associated Events**: Which events this parameter belongs to

#### Example Event Parameter Configuration
```json
{
  "name": "transaction_id",
  "data_type": "string",
  "required": true,
  "allowed_values": [],
  "description": "Unique identifier for the transaction",
  "events": ["purchase", "refund"]
}
```

### Item Parameters
Item parameters are used for nested objects within events, typically for product or item-related data.

#### Creating a New Item Parameter
1. Click "Add new entry" in the Item Parameters section
2. Configure similar to event parameters, with additional options:
   - **Expected Pattern**: Regex pattern for validation
   - **Additional Conditions**: Complex validation rules

#### Example Item Parameter Configuration
```json
{
  "name": "product_id",
  "data_type": "string",
  "required": true,
  "expected_pattern": "^[A-Z0-9]{8}$",
  "description": "Unique product identifier",
  "events": ["purchase", "add_to_cart"]
}
```

## Advanced Configuration

### Parameter Management

#### Allowed Values
- **Adding Values**:
  1. Click the "Add" button in the Allowed Values section
  2. Enter the value manually or select from historical values
  3. Click "Add" to include it in the list

- **Historical Values**:
  - View unique values from the last 30 days
  - Click any value to quickly add it to allowed values
  - Values already in allowed values are highlighted

#### Additional Conditions
- **Creating Conditions**:
  1. Click "Add Condition" in the Additional Conditions section
  2. Select the parameter to validate
  3. Choose the condition type
  4. Enter the expected value

- **Condition Types**:
  - **Equals**: Exact match required
  - **Matches Pattern**: Regex pattern match
  - **Does Not Equal**: Value must be different
  - **Does Not Match Pattern**: Must not match pattern

### Data Type Support

#### Available Types
- **String**: Text values
- **Number**: Numeric values
- **Boolean**: True/false values
- **Array**: Lists of values
- **Object**: Nested data structures
- **Date**: Date values
- **Datetime**: Date and time values
- **Time**: Time values
- **Null**: Null values
- **Undefined**: Undefined values

#### Type-Specific Validation
- **String**: Can include pattern validation
- **Number**: Can include range validation
- **Array**: Can specify item type
- **Object**: Can define required properties

## Interface Features

### Table View

#### Expandable Rows
- Click the arrow (▶) to expand/collapse
- Shows all configuration options
- Allows inline editing

#### Sorting and Filtering
- Click column headers to sort
- Use the search box to filter by name
- Use dropdown filters for specific fields

#### Quick Actions
- **Duplicate**: Creates a copy with "copy_" prefix
- **Edit**: Opens inline editing form
- **Delete**: Removes the entry (with confirmation)

### Form Controls

#### Text Inputs
- **Name**: Alphanumeric characters only
- **Description**: Free text
- **Pattern**: Regex pattern for validation

#### Dropdowns
- **Data Type**: Select from available types
- **Required**: True/False selection
- **Events**: Multi-select for event association

#### Date Pickers
- **Alert From Date**: Select date from calendar
- Format: YYYY-MM-DD

#### Array Inputs
- **Allowed Values**: Add/remove values
- **Events**: Add/remove event associations
- **Conditions**: Add/remove validation conditions

## Best Practices

### Naming Conventions
1. **Events**:
   - Use lowercase with underscores
   - Be descriptive but concise
   - Example: `purchase_complete`, `add_to_cart`

2. **Parameters**:
   - Use camelCase
   - Be specific about the data
   - Example: `transactionId`, `productPrice`

3. **Patterns**:
   - Use clear, documented patterns
   - Test patterns before saving
   - Example: `^[A-Z0-9]{8}$` for 8-character alphanumeric

### Parameter Configuration
1. **Data Types**:
   - Choose the most specific type
   - Consider validation needs
   - Document any special requirements

2. **Required Fields**:
   - Mark critical fields as required
   - Consider optional fields carefully
   - Document why fields are required

3. **Validation Rules**:
   - Start with basic validation
   - Add complex rules as needed
   - Test validation thoroughly

### Event Association
1. **Parameter-Event Mapping**:
   - Associate parameters with relevant events
   - Consider reusability
   - Document relationships

2. **Required Parameters**:
   - Define required parameters per event
   - Consider optional parameters
   - Document requirements

3. **Validation Rules**:
   - Set event-specific rules
   - Consider cross-event validation
   - Document special cases

## Technical Notes

### Data Management
- **State Management**:
  - URL parameters for sharing
  - Session storage for active component
  - Caching for performance

### Performance
- **Lazy Loading**: Loads data as needed
- **Caching**: Stores recent configurations
- **Batch Updates**: Groups changes

### Error Handling
- **Validation**: Checks before saving
- **Error Messages**: Clear feedback
- **Recovery**: Automatic state recovery

### Export
- **Excel Export**: Full configuration export
- **Format**: Structured data
- **Fields**: All configuration details

## Security

### Input Validation
- Validate all inputs
- Sanitize special characters
- Prevent injection attacks

### Access Control
- Proper authentication
- User role restrictions
- Change logging

### Data Protection
- Secure configurations
- Encrypt sensitive data
- Regular backups

## Troubleshooting

### Common Issues
1. **Validation Errors**:
   - Check data types
   - Verify patterns
   - Review required fields

2. **Association Problems**:
   - Verify event names
   - Check parameter names
   - Review relationships

3. **Performance Issues**:
   - Clear browser cache
   - Reduce filter complexity
   - Optimize configurations

### Getting Help
- Check the documentation
- Review error messages
- Contact support if needed