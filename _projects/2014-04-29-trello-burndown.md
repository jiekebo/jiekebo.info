---
layout: project
title: "Trello Burndown"
modified:
excerpt: "Scrum burndown chart for Trello boards."
date: 2014-04-29
tags: [projects]
image:
  feature: trelloburndown.png
---

<div markdown="0"><a href="https://github.com/jiekebo/Trello-Burndown" class="btn">Go to GitHub project ></a></div>

Having been used to Jira and the many ways in which it is possible to track progress, I decided to try and make a burndown chart for Trello. Trello is my weapon of the choice for smaller projects, and working in small teams. There are no rules and everything is possible. 

When using scrum agile approach to development all that freedom comes with great responsibility. For example it is perfectly possible to add tasks to an ongoing sprint, without anyone noticing it. When that happens it is difficult to track whether the team is on target to finish the sprint it set out to do in the beginning. 

Having a burndown chart clearly visualises to all what has happened. You will see a "burnup" whenever new tasks arrive during the sprint. I think it is also a great confidence booster when the team day-by-day sees the burndown nearing the ideal line, knowing that we are on target to a successfull sprint conclusion.

To use this, add your trello api-key to the index file, fetch the id of the board you want a burndown from, and fetch the columns from which tasks are moved from and to. All these id's can be gathered by using the Trello api.

#### Technology stack:

* D3
* Coffeescript
* Bower
* Gulp