---
publish: false
type: person
name: <% tp.file.title %>
birthday: 
title: 
location: 
phone: 
timezone:
company: 
email: 
languages: 
certificates: 
tags:
  - person
created: 
updated:
---

<%*
await this.app.vault.createFolder("/90.00 - People/" + tp.file.title + "/One-on-Ones")
await this.app.vault.createFolder("/90.00 - People/" + tp.file.title + "/Calls")
await this.app.vault.createFolder("/90.00 - People/" + tp.file.title + "/Notes")
-%>

# Person Template

## One on Ones Last 3 Months
```dataview
TABLE
	person AS "Person",
	one-on-one-tone AS "Tone",
	individual-mood AS "Mood",
	individual-risk-level AS "Risk",
	individual-goal-tracking AS "Goals"
FROM
	"90.00 - People/<% tp.file.title %>/one_on_ones"
WHERE
	type = "one-on-one"
SORT
	created DESC
LIMIT 6
```

## Action Items
```tasks
not done
group by folder
tags include #<% tp.file.title.toLowerCase().replace(/ /g, "-") %>-todo
path regex does not match /99.00 - Templates/
```

## Calls
```dataview
list where type = "call" and contains(person, [[<% tp.file.title %>]]) sort title desc
```

## Notes
```dataview
LIST FROM "90.00 - People/<% tp.file.title %>/Notes"
```

## Meetings Attended
```dataview
list where type = "meeting" and contains(attendees, [[<% tp.file.title %>]]) sort created desc
```

## Documents
```dataview
list where type = "documentation" and contains(authors, [[<% tp.file.title %>]]) sort created desc
```

