---
layout: til
title:  "On Software Identities"
date:   2016-04-25 16:05:04 +0800
categories: til
tags: terminal virtualenv
---

## Context
_I moved a virtual environment to a different folder. This was before I did any pip operations so the problem was not immediately apparent. When you create and activate a VE, it stashes the location of your original softwares and exports the ones inside it--namely, pip and python. So because I moved the whole VE, the activate scripts failed to export the VE softwares._

## Lesson
When you're skeptical of which version of what software/command/script you're using, use these two commands:

`type -a command`

or

`whereis program`
