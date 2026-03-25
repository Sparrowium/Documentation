---
banner: "[[wallpaperflare.com_wallpaper(4).jpg]]"
cssclasses:
aliases:
---



```search-bar
only search bar
show starred files
```

This is an official documentation where I will demonstrate my understanding and knowledge about Computer Science and Computer Engineering that I comprehend through books and others sources.


<hr>







<hr>

> [!dashboard]
> > [!stats]
> > > [!stat] Tasks Completed
> > > ```dataviewjs
> > > const todo = dv.page("TODO");
> > > if (todo) {
> > >   const content = await dv.io.load(todo.file.path);
> > >   const completed = (content.match(/- \[x\]/g) || []).length;
> > >   dv.paragraph(completed);
> > > } else dv.paragraph("0");
> > > ```
> > 
> > > [!stat] Total Notes
> > > ```dataviewjs
> > > dv.paragraph(dv.pages("").where(p => p.file.ext === "md").length);
> > > ```
>
> > [!main]
> > > [!topic-columns]
> > > > [!topic] Computer Engineering
> > > > [![](computer-chip-svgrepo-com.svg)](Computer%20Engineering.md)
> > > > The study of Embedded Systems, Architecture, and Circuits Hardware Design
> > > 
> > > > [!topic] Computer Networking
> > > > [![](networking-servers-svgrepo-com.svg)](Computer%20Networking.md)
> > > > The study of Networking Systems, Administration, and Infrastructure.
> > > 
> > > > [!topic] Computer Science
> > > > [![](computer-code-svgrepo-com.svg)](Computer%20Science.md)
> > > > The study of Software, Firmware, and System Designs
>
> > [!todo-recent]
> > > [!todo] 📋 Incomplete Tasks
> > > ```dataviewjs
> > > const todo = dv.page("TODO");
> > > if (todo) {
> > >   const content = await dv.io.load(todo.file.path);
> > >   const lines = content.split("\n");
> > >   const incomplete = lines.filter(l => l.includes("- [ ]"));
> > >   dv.paragraph(incomplete.length ? incomplete.join("\n") : "✅ All tasks completed!");
> > > } else dv.paragraph("*Create a TODO.md file with tasks.*");
> > > ```
> > 
> > > [!recent] 🕒 Recently Modified
> > > ```dataview
> > > LIST
> > > FROM ""
> > > WHERE file.name != "Home" AND file.name != "TODO"
> > > SORT file.mtime DESC
> > > LIMIT 5
> > > ```

<hr>

```contributionGraph
title: ""
graphType: default
dateRangeValue: 180
dateRangeType: LATEST_DAYS
startOfWeek: 0
showCellRuleIndicators: true
titleStyle:
  textAlign: center
  fontSize: 20px
  fontWeight: normal
dataSource:
  type: PAGE
  value: ""
  dateField:
    type: FILE_MTIME
fillTheScreen: true
enableMainContainerShadow: false
mainContainerStyle:
  backgroundColor: "#6496c819"
cellStyleRules:
  - id: Ocean_a
    color: "#8dd1e2"
    min: 1
    max: 2
  - id: Ocean_b
    color: "#63a1be"
    min: 2
    max: 3
  - id: Ocean_c
    color: "#376d93"
    min: 3
    max: 5
  - id: Ocean_d
    color: "#012f60"
    min: 5
    max: 9999
cellStyle:
  minWidth: 4px
  minHeight: 27px

```

<hr>
