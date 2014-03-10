Sound Blaster 16 Readme File
============================

This file contains additional information to supplement the manual.
Please read all the sections before you proceed with the installation.

This file contains the following sections:

    1. Installation
    2. Uninstallation
    3. DOS Environment settings
    4. DOS Audio Driver Support under Windows 95 DOS Box
    5. Using CREATIVE IDE CD-ROM drive in MS-DOS Mode
    6. BLASTER settings under MS-DOS Mode
    7. Full-Duplex Constraints
    8. Online Documentation
    9. Acknowledgments


1. INSTALLATION

   The full installation option requires about 6 MBytes of hard disk
   space for the program files and an additional 2 MBytes for working space. 
   You might need more if your drive is in compressed form.


2. UNINSTALLATION

   Before uninstalling the software package, ensure that all Sound
   Blaster 16 applications are closed. Any Sound Blaster 16 application
   that is running while uninstallation is in progress will not be deleted
   Also, files that are added to the Sound Blaster 16 directory after
   the initial software installation will not be deleted by the
   uninstallation process. You will have to manually delete these files
   after the uninstallation process is completed.

   Some of the files in the Windows directory can be shared by other
   applications. The uninstallation will prompt you when it tries to
   delete these files. You should choose not to delete the files unless 
   you are very sure that the files are no longer used by Windows.


3. DOS ENVIRONMENT SETTINGS

   Some of the existing DOS programs require the presence of MIDI and
   SOUND environments in order for them to work. The Setup program will
   add the SET MIDI and SET SOUND environment lines at the beginning of
   the AUTOEXEC.BAT file.


4. DOS AUDIO DRIVER SUPPORT UNDER WINDOWS 95 DOS BOX

   Some of the DOS applications are developed with Creative's Sound
   Blaster Developer Kit. These applications require the low-level
   DOS audio device drivers to be loaded. To load the DOS audio
   drivers, you need to add the following lines to the CONFIG.SYS file:

   DEVICE=<C:\dir>\DRV\CTSB16.SYS /UNIT=0 /BLASTER=A:220 I:5 D:1 H:5 /WIN95
   DEVICE=<C:\dir>\DRV\CTMMSYS.SYS

   Remarks:

     a. <C:\dir> is the sound directory where the audio software is located.

     b. The /BLASTER parameter specifies the Sound Blaster base I/O port
        address (A), interrupt request line (I), low 8-bit DMA channel (D)
        and high 16-bit DMA channel (H).

     c. The settings in the /BLASTER parameter must tally with the actual
        settings allocated by Windows 95. To find out the actual settings,
        go into Windows 95 DOS box, and type SET and press <Enter> at the
        DOS prompt. You will see one of the lines displayed is:

            BLASTER=A220 I5 D1 H5 P330 T6

        The values after the A, I, D and H are the actual settings to be
        used for the /BLASTER parameter.

        To help you set up the DOS audio drivers, we have prepared a text
        file CONFIG.TXT in the sound directory. This text file contains
        the above lines to specify the DOS audio drivers. The sound
        directory in the text file had been updated by the installation
        program. You just need to update the /BLASTER parameter and copy 
        the lines into the CONFIG.SYS file.


5. USING CREATIVE IDE CD-ROM DRIVE UNDER MS-DOS MODE

   When you open an MS-DOS Mode session, the system will close all other
   active Windows-based or DOS-based programs.  You can return to 
   Windows 95 by typing exit. There are two ways that you can do to open
   an MS-DOS Mode session:

   - Shutdown the system and choose the "Restart the computer in
     MS-DOS Mode" option.

   or

   - Change your MS-DOS session properties by checking the MS-DOS mode box 
     under the Advanced Program Settings. You can specify whether you want
     to use the current MS-DOS configuration, or specify a new MS-DOS
     configuration.

   If you connect Creative IDE CD-ROM drive to the IDE interface that comes
   with your card, you need to do the following steps to make your CD-ROM
   drive work under MS-DOS Mode:

   5.1 Shutdown and restart the computer in MS-DOS Mode

       You need to add the following lines inside the DOSSTART.BAT :

       <C:\dir>\CTLOAD <C:\dir>\DRV\SBIDE.SYS /D:MSCD001 /V /P:1E8,11,3EE
       <C:\win95dir>\COMMAND\MSCDEX /D:MSCD001 /V /M:8

       NOTES:

       a. DOSSTART.BAT is a batch file in the Windows directory.
          It is executed each time you restart in MS-DOS Mode.

       b. <C:\dir> is the sound directory where the audio software is located.

       c. <C:\win95dir> is the Windows 95 directory.

       To help you set up the DOS audio drivers, we have prepared a
       text file DOSSTART.TXT in the sound directory. This text file
       contains the above lines to specify the DOS CD-ROM drivers.
       The sound directory in the text file has been updated by the
       installation program. You don't need to change any of the parameters.

   5.2 Changing MS-DOS session properties and selecting MS-DOS Mode with
       current configuration

       You need to do the same steps as above.

   5.3 Changing MS-DOS session properties and selecting MS-DOS Mode with
       new configuration

       You need to add the following lines inside the new AUTOEXEC.BAT :

       <C:\win95dir>\CTCM
       <C:\dir>\CTLOAD <C:\dir>\DRV\SBIDE.SYS /D:MSCD001 /V /P:1E8,11,3EE
       <C:\win95dir>\COMMAND\MSCDEX /D:MSCD001 /V /M:8

       NOTES:

       a. <C:\dir> is the sound directory where the audio software is located.

       b. <C:\win95dir> is the Windows 95 directory.

       c. Make sure that the settings in the /P parameter tally with the
          actual settings allocated by Windows 95.


6. BLASTER settings under MS-DOS Mode

   Whenever you change your Audio hardware configuration manually, the
   BLASTER environment under MS-DOS Mode will only be valid after you reboot
   the system once.

   However, if you proceed to MS-DOS Mode without rebooting, you need to run
   CTCM.EXE which is in your Windows directory.  This program makes the
   BLASTER environment tally with the actual hardware settings.


7. FULL-DUPLEX CONSTRAINTS

   Your audio card supports full-duplex recording and playback. However, to 
   make full use of this feature, please make sure you observe the following 
   constraints:

   a. Start only one session of simultaneous playback and recording.  
   b. Use the same sampling rate for both operations.
   c. Preferably play back and record audio files which are in uncompressed 
      (that is, Pulse Code Modulation or PCM) wave format.
   d. Reduce the sampling rate for both operations if your audio playback 
      and recording session is too slow.

   NOTE: The Full-Duplex and DirectSound capabilities are mutually exclusive. 
	 If you activate the full-duplex feature, the DirectSound capability 
         cannot be enabled. And vice versa.


8. ONLINE DOCUMENTATION

   To help you get information on the applications in this package easily,
   we have compiled a set of online documentation which can be accessed from 
   your audio card's program group.  Just click the START button on your 
   Windows 95 taskbar. Select "Programs", followed by "Sound Blaster 16" and 
   then "User's Guide".


9. ACKNOWLEDGMENTS

   MS-DOS, Windows 3.x and Windows 95 are trademarks of Microsoft Corporation.
   All other products are trademarks or registered trademarks of their 
   respective owners.

          **********  E N D   O F   R E A D M E  **********
