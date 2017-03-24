# doskey
Set up Persistent Aliases in Windows

1. [Create your `aliases.cmd` file](https://gist.github.com/vladikoff/38307908088d58af206b) with your *doskey* commands, put it somewhere in Application Data. I put it here: "C:\Users\$USERNAME\AppData".

	@echo off

	DOSKEY ls=dir
	DOSKEY cd=cd $1$Tdir
	DOSKEY clear=cls

2. Configure it to be started automatically whenever you open *cmd*. The setting is in Registry. In Windows 10, in the search box on the taskbar, type regedit.
* Find `HKCU\SOFTWARE\Microsoft\Command Processor`. HKCU might be HKEY_CURRENT_USER.
* Right click, and click `New`. 
* Select `String Value`.
* Rename to "AutoRun".
* Change data to the path where your aliases are saved. In my case: "C:\Users\$USERNAME\AppData".

[Other source](https://superuser.com/questions/302194/automatically-executing-commands-when-a-command-prompt-is-opened/302553#302553).