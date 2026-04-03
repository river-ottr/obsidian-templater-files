# Tags 
#daily 
<%*
// Formatting of daily notes and weeks (Must be a full date for features to work)
// WARNING: this will desync your previous daily notes and is not synced across other templates. Consider Regex updates as well when changing formats.
const daily_format = "MM-DD-YYYY";
const weekly_format = "w YYYY";

const scanning_regex = /\d{2}-\d{2}-\d{4}/;

let path = "bins/daily-notes/";
let path_moment =  "YYYY/MMMM/";
 
let daily_title = "";
if (scanning_regex.test(tp.file.title)){ // listen event on file creation. regex is our protection against false flags. we'll assume the date from the title.
  daily_title = tp.file.title;
}
else{ // this will fire when used as a template directly. not correctly named, we'll assume and rename based on today's date.
  daily_title = moment().format(daily_format);
  await tp.file.rename(daily_title);
}

// Moves the daily note into the daily note path.
// As a simple check, we won't move the note if the path is empty (no path set) or if we'd collide (note already exists) 
if (path != "" || path_moment != ""){
  const daily_path = path + moment(daily_title, daily_format).format(path_moment);
  let file_already_exists = await tp.file.exists(daily_path + ".md");
  if(!file_already_exists){
    await tp.file.move(daily_path + tp.file.title);
  }
}

// Adjacent days as smart links, based on what week we decided this note is above
const yesterday_title = moment(tp.file.title, daily_format).subtract(1, "d").format(daily_format);
const tomorrow_title = moment(tp.file.title, daily_format).add(1, "d").format(daily_format);
const weekly_title = "Week " + moment(tp.file.title, daily_format).format(weekly_format);
%>
<< [[<% yesterday_title %>]] | [[<% tomorrow_title %>]] >>
\>> [[<% weekly_title %>]] <<
### Goals/Tasks:
- [ ] 
### Daily Synopsis
