# Tags 
#daily 
<%*
let daily_title = "";
if (/\d{2}-\d{2}-\d{4}/.test(tp.file.title)){ // listen event on file creation. regex is our protection against false flags. we'll assume the date from the MM-DD-YYYY format.
  daily_title = tp.file.title;
}
else{ // this will fire when used as a template directly. not correctly named, we'll assume and rename based on today's date.
  daily_title = moment().format("MM-DD-YYYY");
  await tp.file.rename(daily_title);
}
%><%* // Adjacent days as smart links, based on what week we decided this note is above
const yesterday_title = moment(tp.file.title, "MM-DD-YYYY").subtract(1, "d").format("MM-DD-YYYY");
const tomorrow_title = moment(tp.file.title, "MM-DD-YYYY").add(1, "d").format("MM-DD-YYYY");
const weekly_title = "Week " + moment(tp.file.title, "MM-DD-YYYY").format("w YYYY");
%>
<< [[<% yesterday_title %>]] | [[<% tomorrow_title %>]] >>
\>> [[<% weekly_title %>]] <<
### Goals:
- [ ] Medication (Morning)
- [ ] Medication (Night)
      
- [ ] Brush Teeth
- [ ] Shave
- [ ] Deodorant
- [ ] Shower
- [ ] Laundry
- [ ] Dishes
      
- [ ] Coffee
- [ ] Breakfast
- [ ] Dinner
      
- [ ] Sketch (that you like!)
- [ ] Journal Entry
### Notes for today
