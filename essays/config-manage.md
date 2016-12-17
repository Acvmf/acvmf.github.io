---
layout: essay
type: essay
title: Configuration Management
date: 2016-09-13
labels:
  - Reflection
  - Config
---

## Welcome to the control center
Configuration management is an important skill for anyone who works with software.
There are plenty of programs which help with this - Subversion, GitHub, even the old but strong SCCS built into Unix.
No large-scale project has been successful without some amount of version control, even if only one developer has worked on it.
I'd like to take a moment to explore what makes this part of software engineering so vital, and how we can go about using it to benefit our projects.

## Version History
Everyone has wished for an undo button in real life. You dropped an egg on the floor, or said something before you thought it through.
It happens, and we all recognize the feeling of regret. Now, with version control, you no longer have to feel like the "before" part of an infomercial!
This is a simple technology - which I'm using as I upload essays to my github.io page - used to keep a copy of all changes made to a piece of software.
This could be anything which is stored in data. The version control software simply makes a note of what you've done.
Therefore, if you mess up, you only need to tell the software to roll back to a previous version.
The entire history of your work is there, so you can revert to a working copy and make incremental changes until you figure out what went wrong.

