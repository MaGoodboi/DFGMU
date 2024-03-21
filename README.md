# DFGMU
Programs Created to Emulate DIR and CD
# rdir.exe && rcd.exe

## Description

#I created these short programs as a project for a graduate class at George Mason University's Digital Forensics Program. I am not a developer by trade, so while these programs
may not be completely efficient in style or efficacy, they do work. 

#RDIR.EXE
#The rdir.exe program will list the files of a directory, and defaults to the current directory if none is provided.
#It will accept the arguments for a directory of choosing, e.g., <E:\>, and /a for show all files, included hidden files; /o to show file owners;
#and /d for all subdirectories. This program is only made for short-string characters and will not work with wide-string characters such as Unicode.

#RCD.EXE
#The rcd.exe program provides the same functionality as the "cd" command in Windows (CAVEAT - it will not change the directory of the parent process, e.g., it will
not change the current working path in a Windows shell). It will accept any argument for a new directory, such as <E:\> or <..>. It relies on SetCurrentDirectoryA for
its functionality and therefore is only built for ANSI characters, same as RDIR.EXE.

#No installation is required to use the program. Download the code or the executable, change the directory to where you saved it, and run from command line:
#Example C:\Users\Desktop: rdir.exe /a /o /defaults
#Example C:\Users\Desktop: rcd.exe ..
#Example C:\Users\Desktop: rcd.exe E:\
