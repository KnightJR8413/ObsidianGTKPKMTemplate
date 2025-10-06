---
name: <%* let name = await tp.system.prompt("Name") %> <% name %>
tags:
  - gtd
  - project
  - <% tp.user.in1ToIn2(name, " ", "_") %>
  - root/file
  - <%* let aof = (await tp.system.multi_suggester((item) => item.basename, app.vault.getMarkdownFiles().filter(file => file.path.startsWith("2_Areas of Focus/")), false, "Which Area of Focus is it apart of")).map(f => `${f.basename}`).join("\n!!-!").replaceAll(" ", "_") %> <% tp.user.in1ToIn2(aof, "!", " ") %>
  - <%* let goal = (await tp.system.multi_suggester((item) => item.basename, app.vault.getMarkdownFiles().filter(file => file.path.startsWith("1_Goals/")), false, "Which Goals is it apart of")).map(f => `${f.basename}`).join("\n!!-!").replaceAll(" ", "_") %> <% tp.user.in1ToIn2(goal, "!", " ") %>
---
<% tp.file.move("3_Projects/" + name + "/" + name) _%>
<%* if ( false ) { %>
#template 
<%*
} _%>
## Defining purpose and principles


## Outcome visioning


## Brainstorming


## Organizing


## Identifying Next Actions


## Supporting Material

```dataview
LIST
FROM #<% tp.user.in1ToIn2(name, " ", "_") %> AND "Notes/"
```


