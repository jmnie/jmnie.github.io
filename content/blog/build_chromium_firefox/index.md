---
title: Build Chromium and FireFox from Source Code (Windows as Example)
date: "2021-03-17"
description: "This blog is a note recording the problems met when building chromium and firefox from source code."
---

## Preface 

Build project from source code is always an interesting stuff. This blog is about how to build chromium and firefox from source code.

Note: Actuallt it's not a blog, it's a small guidance for how to get through the whole workflow (Especially in some regions requiring proxy or VPN to access the chromium source code repository.)


## Build chromium from the source code

## Reference Links 

The guidance is edited from an internal wiki page. Tried several times, very useful. Before the main content, here are some useful official links for Chromium project:

Here is the official link for building chromium on different platforms:
[The Chromium Projects](https://www.chromium.org/developers/how-tos/get-the-code)

Official Guidance for building Chromium for Windows (A little verbose and more universal):
[Build Chromium on Windows](https://chromium.googlesource.com/chromium/src/+/master/docs/windows_build_instructions.md)

[Chromium Embedded Framework, CEF](https://bitbucket.org/chromiumembedded/cef/src/master/) is a project for maintaining different branches of chromium source code and related work of chromium itself. 

Here are 3 links that's useful in building chromium from the CEF project:

It's a wrap-up link for setting up on different OS. 
[Build QuickStart](https://bitbucket.org/chromiumembedded/cef/wiki/MasterBuildQuickStart.md)

A description which involves more details in environment variables and related configuration (on Windows).
[Build Setup](https://bitbucket.org/chromiumembedded/cef/wiki/AutomatedBuildSetup.md#markdown-header-windows-configuration)

## Guidance 

### Pre-requisites

| Actions                      | Remark                                      |  Reference  |
| ----------                   | ----------                                  | ---------- |
| Install Visual Studio 2019   | Community Edition has met the reuqirement. \\     |            |