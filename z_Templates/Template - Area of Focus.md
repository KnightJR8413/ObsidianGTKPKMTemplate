---
name: <%* let name = await tp.system.prompt("Name") %> <% name %>
tags:
  - gtd
  - <% tp.user.in1ToIn2(name, " ", "_") %>
  - root/file
  - area_of_focus
---
<% tp.file.move("2_Areas of Focus/" + name + "/" + name) _%>
<%* if ( false ) { %>
#template 
<%*
} _%>

```dataview
LIST
FROM "3_Project" AND #project AND #root/file AND #<% tp.user.in1ToIn2(name, " ", "_") %>
```
```dataview
LIST
FROM "<%"2_Areas of Focus/" + name %>" AND #sub_area_of_focus
```
```dataview
LIST
FROM "1_Goals" AND #<% tp.user.in1ToIn2(name, " ", "_") %> AND #root/file AND #goal
```
