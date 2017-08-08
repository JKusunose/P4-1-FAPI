# P4-1-FAPI
 Flash-angles pulse inversion imaging for P4-1 transducer (P4-1FAPI)
 
 **Description:**
   This is a multi-angle plane-wave ultrasound contrast-imaging sequence specifically written and optimized for the P4-1 phased array transducer to be operated on the Verasonics Vantage Research Ultrasound System. The sequence is based upon the Flash-angles method, a plane-wave imaging method with multiple steering angles provided by Verasonics. Pulse-inversion was implemented onto the Flash-angles method to achieve contrast imaging, and variables were empirically optimized for microbubble imaging. 

File name: SetUpP4_1FAPI.m 

**General Instructions**

To use the code, you must have the Vantage Verasonics system, Matlab, as well as the package of matlab scripts provided through Verasonics installed onto your computer. Open matlab and set the Vantage folder (with all the Verasonics scripts) as your main folder. To use the P4-1 FAPI code as is, create a P4-1FAPI.mat file by running the setupP4-1FAPI script. Once the matfile is created and placed inside the folder called "matfiles", run VSX and use the P4-1FAPI code, while the appropriate transducer is attatched. 

Several things can be modified with relative ease in the script to suite your needs. The following are some of the   
* To change the depth of the *image window*, adjust the P.startDepth and P.endDepth. The numbers are represented in wavelength
* Change Na to adjusted the *number of acquisition angles* (currently set to 7). The range of acquisition angles (curretly set -30 to 30 degrees) can be modified by changing the total angle of coverage (set to 60 in the same section)
* Change the Trans.frequency in order to change the *sampling frequency*. THe sampling frequency will be that of 4x(Trans.frequency) in MHz.
* Change the TW (transmit wave) structure to modify the transmit pulse(s). A = *transmit frequency (MHz)*, C = *pulse length* (# of half cycles), D = polarity (-1 = inverted)
* In SeqControl, adjust the SeqControl(2) value, which is set to 200 (us), to change the inter-pulse time. Adjust the SeqControl(3) constant, which is set to 20000 (us) (or 50Hz), to change the image frame rate.
