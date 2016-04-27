---
layout: til
title:  "On Software Identities"
date:   2016-04-26
categories: til
tags: symlinks nginx
---

## Context
_The best practice with nginx configurations is to have separate folders for `sites-available` and `sites-enabled` then just include the latter folder in your `nginx.conf` file. `sites-available` is where your confs are. `sites-enabled` just has symlinks to the ones in the other folder._

## Lesson
You symlink by doing the following command:

`ln -s source_file target_file`

Make sure it's the absolute path. You should be able to nano or vi the symlink as you would the source file.
