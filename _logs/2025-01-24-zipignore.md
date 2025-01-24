---
layout: log
title: "ZipIgnore"
subtitle: "A shortcut to zip using .gitignore"
version: 0.1
toc: true
---

## Reason

For quite some time I've been writing terminal shortcuts for my computer
(See [Unity Opener](https://github.com/GerardGascon/UnityOpener)).

Today I've built a basic shortcut to take into account .gitignore files, as I don't want to manually deselect
them when compressing using the context menu.

It'll probably support other types of .ignore files, but I said .gitignore as it's the only kind I use.

## Code

For now, I only have a Batch file:

> @echo off
> 
> call "C:\Program Files\7-Zip\7z.exe" "a" ^\
> "-xr@.gitignore" "-tzip" "result.zip" %1

## Limitations

For now, as a basic shortcut it only supports the wildcards that 7zip supports.

There's no support for character wildcards like "[Aa]ssets"