---
name: <%* let name = await tp.system.prompt("Name") %> <% name %>
tags:
  - gtd
  - goal
  - <% tp.user.in1ToIn2(name, " ", "_") %>
  - root/file
  - <%* let aof = (await tp.system.multi_suggester((item) => item.basename, app.vault.getMarkdownFiles().filter(file => file.path.startsWith("2_Areas of Focus/")), false, "Which Area of Focus is it apart of")).map(f => `${f.basename}`).join("\n!!-!").replaceAll(" ", "_") %> <% tp.user.in1ToIn2(aof, "!", " ") %>
---
<% tp.file.move("1_Goals/" + name + "/" + name) _%>
<%* if ( false ) { %>
#template 
<%*
} _%>
```dataview
LIST
FROM "3_Projects" AND #Project AND #root/file AND #<% tp.user.in1ToIn2(name, " ", "_") %>
```