---
title: Build Chromium and FireFox from Source Code (Windows as Example)
date: "2021-03-17"
tags: [tech, EN]
description: "This blog is a note recording the problems met when building chromium and firefox from source code."
---

## Preface 

Build project from source code is always an interesting stuff. This blog is about how to build chromium and firefox from source code.

Note: Actuallt it's not a blog, it's a small guidance for how to get through the whole workflow (Especially in some regions requiring proxy or VPN to access the chromium source code repository.)


## Build chromium from source code

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
| **Install Visual Studio**   | Community Edition has met the reuqirement. Note for the installation:    |   [Chromium Offical Docs](https://chromium.googlesource.com/chromium/src/+/master/docs/windows_build_instructions.md)         |
|                              | 1. Desktop development with C++ (including **MFC and   ATL support**)   |                                  |     
|                              | 2. Install Windows 10 SDK installed, latest version is preferred         |                                  |
| **Setup depot_tools**            | [depot_tools](http://commondatastorage.googleapis.com/chrome-infra-docs/flat/depot_tools/docs/html/depot_tools.html) is a tool for maintaing the source (Cubersome to use)  | [depot_tools Doc](http://commondatastorage.googleapis.com/chrome-infra-docs/flat/depot_tools/docs/html/depot_tools_tutorial.html#_setting_up) |
| Add depot_tools to path (system environment variable on Win) | Unzip the folder, or you can git clone the [repository](https://chromium.googlesource.com/chromium/tools/depot_tools.git)  | Add it to the system variables in case                    |
| Add system environment variable **DEPOT_TOOLS_WIN_TOOLCHAIN: 0** | SET DEPOT_TOOLS_WIN_TOOLCHAIN=0 | [Chromium Guide](https://chromium.googlesource.com/chromium/src/+/master/docs/windows_build_instructions.md)  |
| Add system environment variables **GYP_GENERATORS** & **GYP_MSVS_VERSION** |  SET GYP_GENERATORS=msvs-ninja,ninja  |                              |
|                             | SET GYP_MSVS_VERSION=2019 (if you use other versions please chnage)          |                                       |

These are environment settings for preparations of building chromium on Windows. 

### Build Chromium 

After installing the Visual Studio and setting the environment variables, next step is to fetch the source code from Chromium source code repository. The following table is a detailed instruction (Note: ** Follow the step exactly one by one, especially setting the proxy **)

| Phase      | Run Command & Operations             | Running Path  |         Remark                        |
| -----------| ----------------------------| --------------| ------------------------------------- |
| **Prepare**    | netsh winhttp set proxy <url:port>  |                 | **Run the command in CMD** in case did not work |
|            | git config --global user.name <your name>   |         | Set your git use info                            |
|            | git config --global user.email <your email> |         | Set your git use info                            |
|            | git config --global http.proxy <url:port>   |         | Set git proxy                                    |
|            | git config --global https.proxy <url:port>  |         | Note: when set https proxy, use **http://** ,do not use https:// |
|            | set HTTP_PROXY=<url:port>                   |         | Set global proxy                                                  |
|            | set HTTPS_PROXY=<url:port>                  |         | when set https proxy, use **http://** ,do not use https://       |
|            | set SOCKS5_PROXY=<url:port>                 |         | **Compulsory.If SOCKS5 is not set, will encounter problems when running scripts in depot_tools** |
|**BOTO config** | This step is also to create the proxy.      |         |                                                                   |
|            | Create a file with extension ".boto", e.g. proxy_config.boto |   |                                                        |
|            | The BOTO content:                           |         |                                                                   |
|            | [Boto]                                      |         | Save the file somewhere you like, for example, C:\proxy_config.boto                                                                   |
|            | proxy=<proxy_url>                           |         |                                                                   |
|            | proxy_port=<proxy_port>                     |         |                                                                   |
|            | **SET NO_AUTH_BOTO_CONFIG=C:\proxy_config.boto** |      | In Windows, add a new variable in system environment variables. |
| **Running gclient** | gclient                    |         | **Run the command in CMD**, it will install an individual python and other tools. |
| **Fetch Master** | fetch chromium                | Parent directory of chromium src directory | Download the source code from master, may take a very long time, depending on the internet connection.                                              | 
| **Update Master** | git checkout master          | chromium src directory            |                             |
|               | git pull                     | chromium src directory            | pull changes list                             |
|               | gclient sync                 | chromium src directory            | synchronize dependencies and third parties                            |
| **Switch to working branch** | git checkout -b <local branch name> <tag name> | chromium src directory |  example: git checkout -b Chromium_39.0.2171.71 39.0.2171.71. Go to [Chrome Calendar](http://www.chromium.org/developers/calendar) to find latest stable branch (tag), in "Current Release Information", win, stable, current_version |
|               |                              |                                   | Note: you may need to run **"git fetch --tags"** to fetch all tags first    
|               | gclient sync --with_branch_heads --jobs 16    | chromium src directory        |  to sync all solution related code, dependencies and third parties of current branch |
| **Generate solution file**  | gn args out/<build name>  | chromium src directory    | for example: gn args out/Default        | 
|                         |                           |                           |  in the opened editor, set at least following build args.       |
|                         |                           |                           | **is_debug=false** |
|                         |                           |                           | **target_cpu="x64"**| 
|                         |                           |                           | See [parameters](https://chromium.googlesource.com/chromium/src/+/master/tools/gn/docs/quick_start.md)                     |
| **Build solution**          | ninja -C out\<build name> chrome | chromium src directory | build x64 bit to src\out\<build name> folder, could take 4 hours |
|                         |                                                           | See [build instructions](https://chromium.googlesource.com/chromium/src/+/master/docs/windows_build_instructions.md) |
|                          |                                                          | Note: you may need to add "C:\Program Files (x86)\Windows Kits\10\Include\10.0.16299.0\um" to PATH system environment variable | 
|                         |                                                           | Note: you may need to modify **"out\Default\environment.x64"** file, changing all 10.0.15063.0 to 10.0.16299.0 (for correct Win SDK version). |  
                                              


## Build FireFox from source code 

Build from FireFox from source code is pretty easier. 

### Reference Links

Here is the link for buidling Firefox on Windows (won't paste the content here, just follow the instructions):

[Build FireFox on Windows](https://firefox-source-docs.mozilla.org/setup/windows_build.html)

Remarks on the note:
1. Install Python 3.x and Python 2.7 (not sure why the script still requires Python2 dependency, and set the environment variables on Windows if multiple versions of Python did not work as expected )
2. When set the system proxy, remember to set the following:
   - http proxy
   - https proxy (when set https proxy, use http://your_proxy removing 's')
   - socks5 proxy (crucial)
3. If the toolchain 'mach' failed on certain steps, just perform some other actions.

### Building Old Versions FireFox
(This section is added on 2021/04/08 ) When build FireFox with some lower versions, there are several problems I have seen:
1. The Rust version is not compatiable
2. The script (Mainly in Python, for the purpose to update) needs to sync with the server and check the versions. 