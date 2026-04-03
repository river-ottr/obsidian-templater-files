## tldr: my settings for these templates

### Daily notes -- Built in Plugin
- Date format: YYYY/MMMM/MM-DD-YYYY
- New file location: bins/daily-notes
- Template file location: _templates/t_daily
- Open daily note on startup: OPTIONAL

### Unique note creator -- Built in Plugin
- New file location (up to you): _categorization-request
- Template file location: _templates/t_random
- Unique prefix format(doesn't matter, note renamed on creation): BLANK

### Templater -- Community Plugin
critical settings mentioned below, others ommitted
- Trigger Templater on new file creation: YES
- Enable file regex templates: YES
 - Week (\d|\d{2}) \d{4}, _templates/t_weekly.md
 - \d{2}-\d{2}-\d{4}, _templates/t_daily.md

### Backlinks -- Built in Plugin (Optional, Recommended)
- Show backlinks at the bottom of notes: YES

## too long did read:

- Features a previous and next note links for daily and weekly notes.
- Furture and past proof (by assuming the date from title). Notorius busy work for gaps in daily notes.
- Scroll through time and entires without leaving your notes.
- With the use of the Backlinks plugin, you can see what notes you made on that day and what the day of the files creation was like.
- Easily customize the static text of your daily notes. The script automation affects titles, dates, links and file relocation so you can focus on writing.
- Link your notes together based on the date of creation.
- Prevents collision of random notes using timestamps for titles.
