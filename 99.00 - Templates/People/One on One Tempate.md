---
<%*  
const folderPath = tp.file.folder(true);  
const folderArray = folderPath.split("/");
const personName = folderArray[folderArray.length - 2];
-%>
publish:
type: one-on-one
person: "[[<%* tR += personName %>]]"
one-on-one-tone:
individual-mood:
individual-risk-level:
individual-goal-tracking:
tags:
created:
updated:
---
#  <% tp.date.now("YYYY.MM.DD") %> One-on-One with <%* tR += personName %>

- One on One Tone: `INPUT[inlineSelect(option(Professional),option(Normal), option(Tense)):one-on-one-tone]`
- Individual Mood: `INPUT[inlineSelect(option(Happy), option(Excited), option(Grateful), option(Loving), option(Proud), option(Hopeful), option(Content), option(Peaceful), option(Relaxed), option(Inspired), option(Focused), option(Energetic), option(Calm), option(Sad), option(Lonely), option(Bored), option(Frustrated), option(Angry), option(Anxious), option(Nervous), option(Confused), option(Jealous), option(Guilty), option(Embarrassed), option(Tired)):individual-mood]`
- Individual Goals are `INPUT[inlineSelect(option(N/A),option(On Track), option(Off Track)):individual-goal-tracking]`
- Individual Risk Level: `INPUT[inlineSelect(option(Low), option(Medium),option(High),option(Critical)):individual-risk-level]`

## Discussion Log

### Department Updates
- Item 1
- Item 2

### Individual Updates
- Item 1
- Item 2 

### Action Items
- [ ] Item 1 #<%* tR += personName.toLowerCase().replace(/ /g, "-") %>-todo
- [ ] Item 2 #<%* tR += personName.toLowerCase().replace(/ /g, "-") %>-todo
