---
title: Setup
---

You will need the following software installed and working correctly on your system to be able to follow the course.

> ## Common Issues & Tips
> If you are having issues installing or running some of the tools below,
check a list of [common issues](./common-issues/index.html) other course participants encountered and some useful tips for using the tools and working through the material.
{: .callout}

## Command Line Tool
You will need a command line tool (shell/console) in order to run Python scripts and version control your code with Git.
- On Windows, it is **strongly** recommended to use **Git Bash** (which is included in
  [Git For Windows package](https://gitforwindows.org/) - see the Git installation section below). The use of 
  Windows command line tool `cmd` is not suitable for the course. We also advise against using 
  [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/) for this course as we do not 
  provide instructions for troubleshooting any potential issues between WSL and PyCharm.
- On macOS and Linux, you will already have a command line tool available on your system. You can use a command line tool such as [**Bash**](https://www.gnu.org/software/bash/),
  or any other [command line tool that has similar syntax to Bash](https://en.wikipedia.org/wiki/Comparison_of_command_shells),
  since none of the content of this course is specific to Bash. Note that starting with macOS Catalina,
  Macs will use [Zsh (Z shell)](https://www.zsh.org/) as the default command line tool instead of Bash.

To test your command line tool, start it up and type:
~~~
$ date
~~~
{: .language-bash}

If your command line program is working - it should return the current date and time similar to:
~~~
Wed 21 Apr 2021 11:38:19 BST
~~~
{: .output}

{% include links.md %}
