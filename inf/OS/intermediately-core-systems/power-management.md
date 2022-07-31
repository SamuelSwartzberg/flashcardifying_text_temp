https://en.wikipedia.org/wiki/Hibernation_(computing)

`shutdown`|shutting your system down
reboot|restart your computer
shutdown{ ‹option›}[ ‹shudown-time›][ ‹wall-message›]

caffeinate creates assertions to alter system sleep behavior. 
If no assertion flags are specified, caffeinate creates an assertion to prevent idle sleep.  
If a utility is specified with -u, the caffeinate assertions will persist for the duration of the utility's execution. 
if no utility is specified with -u, caffeinate creates the assertions directly, and those assertions will persist until caffeinate exits, or until the timeout specfied w/ -t.