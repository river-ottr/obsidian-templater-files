creation date: [[<% tp.date.now("MM-DD-YYYY") %>]]<%* 
// automatically links to associated daily note, weekly note
// and generates a unique filename based on the time of creation.
let new_title = moment().format("YYYYMMDDHHmmss");
await tp.file.rename(new_title); %>
\>> [[Week <% tp.date.now("w YYYY") %>]] <<
tags: #categorization-request
#### Author's Notes:

### Entry: 
