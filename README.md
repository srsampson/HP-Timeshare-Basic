#### HP2000-TSB Time Shared BASIC - Access version

HP2000/Access, Date code 1812, which was the last release of OS in the HP2000 family of computer systems.
A date code of 1812 is understood to translate to the 12th week of 1978.

This repository is run on Ubuntu with the simh apt-get package installed.

Open two command line windows. On the first type:
```
hp2100 asmain
```
When it comes up to a prompt, go to the other window and type:
```
hp2100 asiop
```
You see, the TSB system is actually run on two computers talking to each other over the bus, in this case TCP/IP, with the IOP being used for I/O and buffers, and the main used for the OS.

Note: After you stop the simulator, you may have to wait a couple minutes to start it again. It seems the TCP/IP bus connection needs to time-out. You'll get an I/O error if you try to start too fast.

This repository is the result of a system build, and contributor tapes, and then a SLEEP. There is also a HIBERNATE tape in the tapes directory. So to start the system up and allow telnet connections, you just have to answer a few questions and type in the date and time. The date is julianday/2-digit year and time is 24 hour clock.

This is what it looks like:

```
MAG TAPE SELECT CODE? 16
2754? Y
LOAD WHICH MODULE? 2883
SYSTEM GENERATION? N
MAG TAPE RELOAD?
LOAD OR DUMP COMMANDS?
DATE? 199/22
TIME? 1516
HP22687A-1812
```

At this point you are the system console, and you can type SYSOP commands, as given in the operators guide.

When you open a command window, type:

```
telnet localhost 2323
```
You hit return a couple times, and then a ^j (for linefeed) and it will prompt you to logon.

The file:
```
accounts.txt
```
Shows the accounts that are set up. The passwords are the same as the userid, so when logging-in:
```
HELLO-C906,C906
```
The password is after the comma.

The A000 account is the superuser.

When you are finished and want to stop the simulation, you MUST do a:
```
SLEEP
```
Then just hit return a couple times and you will be back to the simulator, where you can type 'q'.

If you don't SLEEP or the system crashes, you will have to rebuild the system, or load the hibernate tape. Instructions are in the ```hp2000-access-installation-and-operation.pdf``` guide.

#### HP2000 BASIC
This was a very powerful BASIC interpreter. It had both Random and Serial Files, and features like PRINT USING for formated output. The String syntax was superior to Microsofts method (in my opinion). There's also User Groups as well as System Library directories, which was an excellent way to provide levels of security for students.

#### NOSTALGIA
This simulation of the HP2000 Time Share Basic is from another era. There were some attempts at user security, but with 100's of students,
the computer was under attack almost every day by a very small minority. You never knew if a system crash was a bug, or if some student found
a way to blow-up the system. The SYSOPS were heavy coffee drinkers. Today, I would not recommend you put this online, and have your router
redirect Telnet users. Nope... No siree Bob!

At my high school the county had the contributed programs in the LIB (library), and each school would have a GROUP, which the teachers could make execute-only and not source code readable, and then the normal student files were in the CAT (catalog). Student Aid's would get a separate account to store their work away from the class.
