# Metadata Profiles

This repository contains metadata profile definitions for categorizing and organizing content for use with https://github.com/jaykobdetar/OpenArchiver. Each profile defines the structured fields used to catalog specific types of content.

## Profile Structure

All profiles are JSON files containing:
- `id`: Unique identifier for the profile
- `name`: Display name for the profile type
- `description`: Brief description of what content this profile covers
- `fields`: Array of field definitions for metadata capture

## Available Profiles

### Interview Profile (`interview.json`)

Used for cataloging all types of interviews including TV, radio, podcast, and print interviews.

**Fields:**
- `show` (select, optional) - The show/network that conducted the interview
- `interviewee` (text, required) - Person being interviewed
- `date` (date, required) - Date the interview was conducted
- `mainstream` (boolean, optional) - Whether conducted by mainstream media outlet
- `purposeful` (boolean, optional) - Whether interview focuses on specific subject vs general
- `topics` (tags, optional) - Topics discussed in the interview
- `platform` (select, optional) - Original distribution platform
- `live` (boolean, optional) - Whether aired live
- `interviewer` (text, required) - Primary person conducting interview
- `in_person` (boolean, required) - Whether conducted in person
- `language` (select, required) - Primary language (English/Spanish/Other)
- `format` (select, required) - Format type (Video/Audio/Text/Other)
- `source` (text, required) - Where the archive obtained the interview
- `duration` (number, optional) - Length in seconds

## Field Types

- `text` - Single-line text entry
- `textarea` - Multi-line text entry for longer content
- `select` - Dropdown selection from predefined options (single choice)
- `multiselect` - Dropdown selection allowing multiple choices
- `boolean` - True/false checkbox
- `date` - Date picker (YYYY-MM-DD)
- `datetime` - Date and time picker
- `number` - Numeric value
- `tags` - Multiple tag entries with free-form input

## Usage

These profiles are designed to work with the Archive Tool application. When adding content to the archive:

1. Select the appropriate profile type
2. Fill in all required fields
3. Add optional fields as applicable
4. Use consistent naming conventions for people and organizations

## Contributing

When adding new profiles:
1. Follow the existing JSON structure
2. Use snake_case for field names
3. Provide clear descriptions for each field
4. Include sensible default values where appropriate
5. Update this README with the new profile documentation

## Notes

- The `Other` option in select fields allows for edge cases not covered by predefined options, it is recommended to update the metadata profile to avoid needing to actually use it
- Duration should always be in seconds for consistency
- Dates should use YYYY-MM-DD format
- Datetime fields should use ISO 8601 format (YYYY-MM-DDTHH:MM:SS)
- Boolean fields should be null if unknown, rather than defaulting to false
- Textarea fields are ideal for longer content like descriptions or notes
- Multiselect fields allow categorizing content under multiple options