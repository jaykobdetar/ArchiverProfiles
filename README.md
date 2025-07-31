# Metadata Profiles

This repository contains metadata profile definitions for categorizing and organizing content for use with https://github.com/jaykobdetar/OpenArchiver. Each profile defines the structured fields used to catalog specific types of content.

## Profile Structure

All profiles are JSON files containing:
- `id`: Unique identifier for the profile
- `name`: Display name for the profile type
- `description`: Brief description of what content this profile covers
- `fields`: Array of field definitions for metadata capture

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

## Available Profiles

### Interview Profile (`Interviews.json`)

Used for cataloging all types of interviews including TV, radio, podcast, and print interviews.

**Fields:**
- `show` (select, optional) - The show/network that conducted the interview
- `interviewee` (text, required) - Person being interviewed
- `date` (date, required) - Date the interview was conducted
- `purposeful` (boolean, optional) - Whether interview focuses on specific subject vs general
- `topics` (tags, optional) - Topics discussed in the interview
- `platform` (select, optional) - Original distribution platform
- `live` (boolean, optional) - Whether aired live
- `interviewer` (text, required) - Primary person conducting interview
- `in_person` (boolean, required) - Whether conducted in person
- `language` (select, required) - Primary language (English/Spanish/Other)
- `format` (select, required) - Format type (Video/Audio/Text/Other)
- `source` (text, required) - Where and how the archive obtained the interview
- `duration` (number, optional) - Length in seconds

### Organization Profile (`Orgs.json`)

Reference records for media companies, shows, networks, and other organizations.

**Fields:**
- `org_id` (text, required) - Unique identifier (e.g., 'fox-news', 'cnn')
- `org_name` (text, required) - Full official name
- `org_type` (select, required) - Organization type (Cable News Network/Broadcast Network/Newspaper/Digital Media/Podcast/etc.)
- `political_leaning` (select, required) - Political orientation (Left/Right/Far left/Far right/Other/Nonpartisan/Unclear)
- `parent_company` (text, optional) - Parent organization if applicable
- `founded_date` (text, optional) - Year founded (e.g., '1996')
- `headquarters` (text, optional) - Primary location (e.g., 'New York, NY')
- `status` (select, required) - Current status (Active/Defunct/Merged/Rebranded/Unknown)
- `key_people` (tags, optional) - Important figures (founders, CEOs, hosts)
- `affiliated_orgs` (tags, optional) - Related organizations
- `notable_shows` (tags, optional) - Major shows or programs
- `website` (text, optional) - Official website URL
- `notes` (textarea, optional) - Additional information
- `last_updated` (date, required) - Date of last update

### Person Profile (`People.json`)

Reference records for individuals including politicians, journalists, commentators, and other public figures.

**Fields:**
- `person_id` (text, required) - Unique identifier (e.g., 'donald-trump', 'joe-biden')
- `full_name` (text, required) - Complete official name
- `person_type` (select, required) - Type of person (Politician/Journalist/TV Host/Radio Host/etc.)
- `political_leaning` (select, required) - Political orientation (Far Left through Far Right/Varies/Nonpartisan/Unknown)
- `party_affiliation` (select, optional) - Political party affiliation
- `current_roles` (tags, optional) - Current positions/jobs (e.g., 'President', 'Fox News Host')
- `former_roles` (tags, optional) - Previous positions/jobs
- `organizations` (tags, optional) - Companies, networks, agencies they work(ed) for
- `birth_date` (date, optional) - Date of birth if public knowledge
- `birth_place` (text, optional) - City, State/Country
- `active_period` (text, optional) - Years active in politics/media (e.g., '2015-present')
- `education` (text, optional) - Highest degree or notable institutions
- `social_media` (tags, optional) - Twitter/X, Truth Social, etc. handles
- `official_website` (text, optional) - Personal or campaign website
- `notes` (textarea, optional) - Additional relevant information
- `last_updated` (date, required) - Date of last update
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
