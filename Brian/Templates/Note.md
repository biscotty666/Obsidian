<%*
  let title = tp.file.title
  if (title.startsWith("Untitled")) {
    title = await tp.system.prompt("Title");
    await tp.file.rename(title);
  } 
  
  tR += "---"
%>
Title:  <%* tR += title %>
Created: <% tp.date.now("dddd Do MMMM YYYY HH:mm") %>
Categories: 
Status: #new
Aliases: 
Tags: 
---

---
# <%* tR += title %>
