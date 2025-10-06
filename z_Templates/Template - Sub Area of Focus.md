---
name: <%* let name = await tp.system.prompt("Name") %> <% name %>
tags:
  - gtd
  - <% tp.user.in1ToIn2(name, " ", "_") %>
  - sub_area_of_focus
---
<% tp.file.move(tp.file.folder(true) + "/" + name) _%>
<%* if ( false ) { %>
#template 
<%*
} _%>