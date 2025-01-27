---
publish: 
type: call
person: "[[<% tp.file.folder(true).split('/').slice(1,2).join('') %>]]"
call-summary:
call-tone:
tags: 
created: 
updated:
---

Call Summary
`INPUT[textArea:call-summary]`

Call Tone: `INPUT[inlineSelect(option(Professional),option(Normal), option(Tense)):call-tone]`

### What is this call about?

### Any action items?