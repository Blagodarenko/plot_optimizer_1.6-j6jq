----------------------------------------------------------------------------------
README

Version 1.6 (11/4/2014)

Updated by j6jq (most recent author with address at: BURST-J6JQ-ZWC2-RK7E-CLY93)
Based on dcct's optimizer (dcct's address: BURST-DCCT-RZBV-NQC7-9G5N2)
----------------------------------------------------------------------------------



----------------------------------------------------------------------------------

BUILD INSTRUCTIONS:

	1. Install mingw64 from link (http://sourceforge.net/projects/mingw-w64/files)
		- Skips _WIN64 sections if not installed
	2. Install Codeblocks if not already installed
	3. Load included Codeblocks project (.cbp file)

----------------------------------------------------------------------------------



----------------------------------------------------------------------------------

HOW TO RUN:

Parameters:
	
	Usage: Optimize <maximum delay in seconds for adequate RAM> <Output directory or -f for same as Input> [-del 0] [-m MEMORY] <Plot file>
		
		'./Optimize' - name of executable file
			       - switch to optimize32 on 32-bit operating system
			       - "./" should not be used on Windows

		'[maximum delay in seconds for adequate RAM]' - Replace with number of seconds to pause until enough free RAM is available

		'<Output directory>' - Directory path where optimized plot file is saved and can be on a different drive
				     - '-f' if you want to use the same directory as the original plot file

		'-del 0' - (optional) specifies if the original plot file should be deleted or not (No in this example)

		'-m 1G' - (optional) specifies the maximum amount of memory that the optimizer can use (???M for MB)

		'<Plot file path>' - File path of plot file to optimize


  Windows Example 1: Optimizer 0 C:\plots\optimized -m 1G E:\plots\<Name of plot file>

	- This will run with a maximum of 1 GB of RAM and the plot file will be saved to "C:\plots\optimized". It will continue to run even if there is not enough memory available.

  Windows Example 2: Optimizer 30 -f -m 1000m E:\plots\<Name of plot file>

	- This will run with a maximum of 1 GB of RAM and the plot file will be saved to "E:\plots". It will wait up to 30 seconds or until there is enough free RAM available (whichever comes first).


Windows - Right click on the included bat file and select Edit. Change parameters to match your computer and plot files.

  Linux Example: ./Optimizer 0 /home/j6jq/Documents/optimized -del 0 -m 1G /home/j6jq/<Name of plot file>

	- This will do the same as Windows Example 1 with a different output directory.



- Version 1.11 is included for a simpler parameter list, but may contain some bugs that were corrected in 1.5. Example 1 does the same as version 1.11.

----------------------------------------------------------------------------------



----------------------------------------------------------------------------------

RELEASE NOTES:


Version 1.6 (11/4/2014):
- Added a del option to give user control whether or not original plot file is kept or deleted


Version 1.5 (10/25/2014):
- Added a feature that will delay a user-specified MAXIMUM number of seconds between processing scoops
	(If mining at the same time, memory usage spikes at the start of a new block. Specify the number of seconds 		it takes for your hard drive to scan all plot files or when the memory spike decreases.)
- Update: Memory usage more accurately represents the user-specified amount


Version 1.1 (10/5/2014):
- Added a feature to use absolute file paths in Windows
- Added a feature to specify output folder in either OS
- Added a feature to check free disk space on Windows (Linux only previously)
- A directory that does not exist will be automatically created in either OS


----------------------------------------------------------------------------------



----------------------------------------------------------------------------------

TIPS:

- The optimize program cannot be in a folder with plots that are currently being mined
- The optimized plot file(output location) cannot be in the same folder as the original plot while it is currently being mined
- Size of the plot file must be at least twice as large as the memory allocated (never should be an issue)
- More memory allocation means less stress on your hard drive, but could nullify the delay feature (constantly processing)
- Tested on 64-bit Windows and 64-bit Ubuntu (32-bit not supported)
- IMPORTANT for Windows: Windows stores memory in contiguous chunks and means that specifying 3 GB of memory or greater may use much more memory than specified. As the program runs, it fragments the memory and must find or force continuous blocks of ram that are almost 1GB long. When it cannot find any, it causes a memory leak into virtual memory. The soludion is to take memory processing away from Windows, but this must be done very carefully (means I know what's best for the computer instead of Windows) to prevent massive memory leaks. I will post an update after I have fully tested a complete memory fix. As a safeguard, you cannot use more than 75% of total system memory.

- FOR NOW, I RECOMMEND THAT YOU LIMIT MEMORY USAGE TO 1GB OR LESS TO PREVENT A MEMORY LEAK (likely caused by Windows), but you can specify more if you want.

----------------------------------------------------------------------------------

Disclaimer:
This software is provided AS-IS. Use of this software means acceptance that the authors are not responsible if you damage your computer. For those worried about this statement, you should realize that a very small memory size will put extra stress on your hard drive and you should find a balance of size versus how much memory you need free for mining. I usually quit mining for maximum memory allocation until the optimization is done.
