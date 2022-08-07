# file-mantab
jetbrains agent for intellij 2022

##Note1: instructions bellow is based on windows, if you are on OS X / Linux, you should change addresses according to your operating system
  be sure that the .jar file full path doesn't contain any spaces

##Note2: Only one javaagent should be used at the same time, if you've replacing/upgrading from other agents, be sure to remove coresponding
  line from vmoptions

  See FAQ bellow for more information
---------------------------------------------------
This agent will activate IDEs & some of plugins!

/--/NOTE: IF YOU'VE ALREADY LOGGED IN INTO YOUR JB ACCOUNT, FIRST LOG OUT OF IT!\--\
/--/NOTE: IF YOU'VE ALREADY INSTALLED "IDE Eval Reset" PLUGIN, UNINSTALL IT FIRST!\--\

1) Copy ja-netfilter-all folder to C:\
	(So path of ja-netfilter.jar file should be C:\ja-netfilter-all\ja-netfilter.jar)

2) Locate .vmoptions file of desired JetBrains product:
	This is located in the bin directory of your JetBrains IDE. For example:
	C:\Program Files\JetBrains\IDEA\bin\idea64.exe.vmoptions

	Or, if you use Custom VM Options, the path would be, for example:

	C:\Users\%username%\AppData\Roaming\JetBrains\IntelliJIdea2021.3\idea64.exe.vmoptions
	(Note: this file won't exist by default, either create it manually
	       or use "Edit Custom VM Options..." inside IDE -> Configure menu if you have access to IDE)

	So if something doesn't work, make sure you change the right file (custom takes precedence over the one in the bin directory)

3) add following line to the end of the .vmoptions file:

-javaagent:C:\ja-netfilter-all\ja-netfilter.jar=jetbrains

4) Run JetBrains product, Select "Activate <IDE NAME>", Select "License Server", Enter Server address: https://jetbra.in, Click activate
	On some PCs, an error of "server did not passed data integrity check" is thrown. In that case, close IDE, open corresponding .vmoptions
	inside C:\ja-netfilter-all\vmoptions folder, and add the same line as step 3 to that .vmoptions too; Then repeat step 4.
	You can also try using Auto vmoptions configurer (see below)

Done!

NOTE: don't care about the activation time (if an activation time is shown), it is a fallback license and will not expire

NOTE: this license can activate Code With Me plugin & most of other plugins!
---------------------------------------------------
NEW Auto configure vmoptions (if not works, use manuall way (step 2 above)): 
    macOS or Linux: execute "scripts/install.sh"
    Windows: double click to execute "scripts\install-current-user.vbs" (For current user)
                                     "scripts\install-all-users.vbs" (For all users)
---------------------------------------------------
FAQ:
Q: Where is the .vmoptions file on OS X / Linux?
A: Use the menu item in the IDE: Gear Icon -> Edit custom VM options
	Note: to access this, you have to activate jetbrains product in trial by creating a free account on JetBrains website & the Activate it fully.

