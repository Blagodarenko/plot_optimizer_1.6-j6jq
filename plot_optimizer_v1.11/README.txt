----------------------------------------------------------------------------------
README

Version 1.1 (10/6/2014) Updated by j6jq (BURST-J6JQ-ZWC2-RK7E-CLY93)
Based on dcct's optimizer (Most of the code belongs to dcct BURST-DCCT-RZBV-NQC7-9G5N2)
----------------------------------------------------------------------------------


----------------------------------------------------------------------------------

COMPILE:

	- Use the included makefile for your OS and architecture (32-bit vs. 64-bit) OR
	- Open the Code::Blocks project file (.cbp) OR 
	- Use your favorite compiler and compile the code from the /src folder

----------------------------------------------------------------------------------



----------------------------------------------------------------------------------

HOW TO RUN:

Parameters:
	
	Usage: optimize64 <Output directory or -f for same as Input> [-m MEMORY] <Plot file>
		
		'./optimize64' - name of executable file
			       - switch to optimize32 on 32-bit operating system
			       - "./" should not be used on Windows

		'<Output directory>' - Directory path where optimized plot file is saved and can be on a different drive
				     - '-f' if you want to use the same directory as the original plot file

		'-m 1G' - (optional) specifies the maximum amount of memory that the optimizer can use (???M for MB)

		'<Plot file path>' - File path of plot file to optimize


  Windows Example 1: optimizer64 C:\plots\optimized -m 2G E:\plots\<Name of plot file>

	- This will run the 64-bit version with a maximum of 2 GB of RAM and the plot file will be saved to "C:\plots\optimized".

  Windows Example 2: optimizer64 -f -m 2000m E:\plots\<Name of plot file>

	- This will run the 64-bit version with a maximum of 2 GB of RAM and the plot file will be saved to "E:\plots".


Windows - Create a .bat file in the same directory and add the parameters needed. Bat file creation is explained on Google if you are unsure how to make one.

  Linux Example: ./optimizer /home/j6jq/Documents/optimized -m 2G /home/j6jq/<Name of plot file>

	- This will do the same as Windows Example 1 with a different output directory.

----------------------------------------------------------------------------------



----------------------------------------------------------------------------------

RELEASE NOTES:

- Added feature to use absolute file paths in Windows
- Added feature to specify output folder
- Added feature to check free disk space on Windows (Linux only previously)
- A directory that does not exist will be automatically created
- Known Issue: Memory allocation may fail when greater than 2GB (I think inherited from 1.0 and will try to fix)

----------------------------------------------------------------------------------



----------------------------------------------------------------------------------

TIPS:

- The optimize program cannot be in a folder with plots that are currently being mined
- The optimized plot file cannot be in the same folder as the original plot while it is currently being mined
- Size of the plot file must be twice as large as the memory allocated (never should be an issue)
- Untested on 32-bit Windows, but tested on 64-bit Windows and 64-bit Ubuntu

----------------------------------------------------------------------------------
