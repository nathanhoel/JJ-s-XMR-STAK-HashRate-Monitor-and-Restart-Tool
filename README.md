	JJ's XMR-STAK HashRate Monitor and Restart Tool

	Based on an idea by @CircusDad on SupportXMR Chat
	His Vega Mining Guide for XMR --> http://vega.miningguides.com/

	How many times have you walked away for your computer to come back
	and notice that your hash rate dropped by HUNDREDS of hashes?
	How many times did you wake up to that scenario and wonder how long it had been going on?
	
	What happens when you go away for a few days with your lady/gentleman or some other sexy creature? 
	If you're like me you stress over your rig! It really kills the mood.
	
	How much potential profit have you lost to this terror!
	
	Well, I have felt your pain and decided to sit down and come up with a solution and here it is.
	How much is your peace of mind worth? If you find that your daily hash rate has now increased
	because this is no longer happening to you I'd appreciate it if you would consider a donation
	toward my hard work.
	
	No amount is too small! I'm not greedy! :-)
	
	XMR: 42JFvWHSSGCFUBSwTz522zXrkSuhZ6WnwCFv1mFaokDS7LqfT2MyHW32QbmH3CL94xjXUW8UsQMAj8NFDxaVR8Y1TNqY54W
	
	Purpose:	To monitor the STAK hashrate. If it drops below the threshold,
			the script is restarted.
				
	Features:	Script elevates itself if not run in Admin context.
			Logging
			The Radeon RX Vega driver is disabled/enabled.
			Any tools defined in the "Start Video Card Management Tools Definitions"
			section below are executed in order.
			Sets developer suggested environment variables
			Miner is started.
			Hash rate is monitored.
			If hash rate falls below the target as defined in the $hdiff variable (default is 100 hashes) 
			or STAK stops responding the miner process is killed.
			Script re-starts itself.
			SMS alerts via Gmail
			Alerts via Slack WebHooks

	*** IMPORTANT NOTE ***: If the script cannot kill the miner it will stop and wait for input.
				Otherwise it would invoke the miner over and over until the PC ran out of memory.
				In testing I have not seen it fail to kill the miner but I need to account for it.
				It will also stop if the miner cannot be found (for obvious reasons)
							
	Requirements:	Elevated privilege (Run as Administrator)
			Enable Powershell scripts to run.

	Software Requirements:	XMR-STAK.EXE - Other STAK implementations are no longer supported.
				By default the script is configured to use the following software:
							
				XMR-STAK.EXE <-- Don't remark out this one. That would be bad.
				OverdriveNTool.exe
				nvidiasetp0state.exe
				nvidiaInspector.exe
							
				If you do not wish to use some or all of them just REMARK (use a #)
				out the lines below where they are defined in the USER VARIABLES SECTION.
				All executable files must be in the same folder as the script.
							
							
	Configuration: See below in the script for configuration items.

	Usage:	Powershell.exe -ExecutionPolicy Bypass -File JJs_HashMonitor.ps1
	
	Future enhancements under consideration:	Move settings out of the script and into a simple
							txt file to make it easier to manage them.
												

	Author:	TheJerichoJones at the Google Monster mail system

	Version: 3.2
	
	Release Date: 2017-12-06

	Copyright 2017, TheJerichoJones

	License: 
	This program is free software: you can redistribute it and/or modify
	it under the terms of the GNU General Public License version 3 as 
	published by the Free Software Foundation.

	This program is distributed in the hope that it will be useful,
	but WITHOUT ANY WARRANTY; without even the implied warranty of
	MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
	GNU General Public License for more details.

	You should have received a copy of the GNU General Public License
	along with this program.  If not, see <http://www.gnu.org/licenses/>.
