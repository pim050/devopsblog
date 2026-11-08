<%*
const name = await tp.system.prompt("Folder name (lowercase, no spaces, e.g. my-new-post)");
if (!name) return;
const title = await tp.system.prompt("Post title", name.replace(/-/g, " "));
await tp.file.move("/" + name + "/index");
tR += `---
title: "${title}"
date: ${tp.date.now("YYYY-MM-DDTHH:mm:ssZ")}
draft: true
---

`;
%>