# Backstage Catalog Examples

This directory contains examples of Backstage catalog entities including groups, users, and organizational structures.

## Files Overview

### `catalog-info.yaml`
Main component definition for the Backstage application itself.

### `catalog-cop.yaml`
Community of Practice (CoP) definition for DevSecOps.

### `groups-example.yaml`
Comprehensive example of different group types including:
- **Departments**: High-level organizational units (engineering, product)
- **Teams**: Specific working groups (platform-team, frontend-team, backend-team, etc.)
- **Hierarchical Structure**: Parent-child relationships between groups

### `users-example.yaml`
Example users with various roles and group memberships:
- Team members and leads
- Cross-functional roles
- Multiple group memberships
- Profile information including display names and emails

### `org-structure-example.yaml`
Complete organizational hierarchy example showing:
- Root organization
- Department-level groups
- Team-level groups
- Users at different levels
- Cross-cutting groups (like architecture council)

## Group Types

The examples demonstrate different group types supported by Backstage:

- `organization`: Root level organizational unit
- `department`: High-level business units
- `team`: Working groups or squads
- `business-unit`: Alternative to department for some org structures

## User Properties

Users can have the following properties:
- `profile.displayName`: Human-readable name
- `profile.email`: Contact email
- `profile.picture`: Avatar URL (typically GitHub avatar)
- `memberOf`: Array of groups the user belongs to

## Usage

1. **For Development**: Use these files as templates when setting up your Backstage catalog
2. **For Testing**: Import these entities to test your Backstage setup
3. **For Reference**: Understand the structure and relationships between entities

## Importing into Backstage

To use these examples in your Backstage instance:

1. Add the catalog locations to your `app-config.yaml`:
   ```yaml
   catalog:
     locations:
       - type: file
         target: ./catalog-info.yaml
       - type: file
         target: ./groups-example.yaml
       - type: file
         target: ./users-example.yaml
       - type: file
         target: ./org-structure-example.yaml
   ```

2. Or use the Backstage UI to register these entities by providing the file URLs.

## Customization

Modify these examples to match your organization:
- Change group names and descriptions
- Update user information
- Adjust the organizational hierarchy
- Add or remove teams as needed
- Update email domains and contact information

## Best Practices

1. **Consistent Naming**: Use consistent naming conventions (kebab-case recommended)
2. **Clear Descriptions**: Provide meaningful descriptions for all entities
3. **Proper Hierarchy**: Maintain clear parent-child relationships
4. **Contact Information**: Include valid email addresses for groups and users
5. **Profile Pictures**: Use consistent avatar sources (GitHub, internal directory, etc.)

## Entity Relationships

- **Groups** can have parent groups and child groups
- **Users** can be members of multiple groups
- **Components** can be owned by users or groups
- **Systems** can contain multiple components and be owned by groups

For more information, see the [Backstage Catalog Documentation](https://backstage.io/docs/features/software-catalog/).
