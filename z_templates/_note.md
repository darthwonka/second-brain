---
subject: 
peoples: 
date: <% tp.date.now('LLL') %>
cover: "https://i.imgur.com/ce8zJha.jpg"
type: note
---
<%*
let name = tp.file.title;
if (name.startsWith('Untitled'))
{
	const extra = await tp.system.prompt("Title");
	name = `${extra}`;
	await tp.file.rename(name);
}
-%>
# <% name %>
<% tp.file.include("[[T]]") %>


