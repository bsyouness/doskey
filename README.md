# doskey
Set up Persistent Aliases in Windows

[Create your `aliases.cmd` file](https://gist.github.com/vladikoff/38307908088d58af206b)

	@echo off

	DOSKEY ls=dir
	DOSKEY cd=cd $1$Tdir
	DOSKEY clear=cls

Command aliases are specific to the console window you configure them on, therefore a startup script will not work. You can do it this way:

 1. Create a batch file (`.cmd`) with your *doskey* commands, put it somewhere in Application Data. I put it here: "C:\Users\$USERNAME\AppData".

 2. Configure it to be started automatically whenever you open *cmd*. The setting is in Registry. In Windows 10, in the search box on the taskbar, type regedit.
* Find `HKCU\SOFTWARE\Microsoft\Command Processor`. HKCU might be HKEY_CURRENT_USER.
* Right click, and click `New`. 
* Select `String Value`.
* Rename to "AutoRun".
* Change data to the path where your aliases are saved. In my case: "C:\Users\$USERNAME\AppData".

[Source](https://superuser.com/questions/302194/automatically-executing-commands-when-a-command-prompt-is-opened/302553#302553).