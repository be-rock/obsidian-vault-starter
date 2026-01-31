---
created: <% tp.date.now("YYYY-MM-DD") %>
meeting_date: <% tp.date.now("YYYY-MM-DD") %>
status:
attended: 
People:
Topics:
tags:
  - meeting
---
# meeting

<%*
// move current file into folder, keep same title
await tp.file.move("/Meetings/" + tp.file.title)
%>

