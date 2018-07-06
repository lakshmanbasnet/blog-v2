---
title: Oracle Database 11g tutorials
date: 2017-04-03
categories:
- technology
layout: post
description: all you need to know starting from very basic to advanced level of administrating Oracle Database 11g R2 edition. Also, this will be a supplement resource for TU Bsc CSIT DBA notes, questions, and solutions. Learn Oracle Database in Nepal
image: "/assets/oracle-dba.jpg"
---

So, this blog post will be all about the **Oracle Database**, lessons from very beginning to advanced level. The contents will be added regularly.

<br>

<div class="ab">

If you are searching for resources for Bsc CSIT Seventh Semester(7th sem), then these are some of the links of the materials I got that might be useful for learning and appearing DBA exams.
<br><br>
<ul>
<li>Database Administration Handbook, short note by Dadhi R. Ghimire available on <a href="http://csitportal.com/wp-content/uploads/2017/02/Database-administration-Handout.pdf" target="blank">csitportal.com</a> </li>

<li>Oracle DBA Concise Handbook(covers 9i to 11g) by Saikat Basak , Oracle Certified Professional on <a href="http://www.conseiller.com.br/wp-content/uploads/2015/05/oracle-dba-concise-handbook.pdf" target="blank">conseiller.com</a></li>
<li>TU CSIT DBA Model/Old Question Collection by  <a href="https://drive.google.com/file/d/0BwOLtlX2QE6xd2E1elVKYU9MTm8/view" target="blank">csitauthority</a></li>
</ul>




</div>

<br>

<br>


I assume that you have already installed Oracle Database Software 11 g R2 edition on your computer.
<br>


All the commands below are to be executed in **terminal/command** prompt.

<br>



<i class="fa fa-check-square-o" aria-hidden="true"></i>
At first lets set the SID

	set ORACLE_SID = xe

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i>
connect to database with sys dba privileges
	
	sqlplus / as sysdba

<br>

After establishing a database connection you can see `SQL>` prefixed in your command prompt. We will be doing all our database queries after this `SQL>`, remember we don't need to write this command. Also, all database queries end with a **semicolon.** `;`
<br><br>
## Some basic commands##
<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> To search for **server parameter file**

	SQL> nomount;

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i>
To Show the server parameter file location

	SQL> show parameter pfile;

<br>
<i class="fa fa-check-square-o" aria-hidden="true"></i>
To Shutdown database

	SQL> shutdown immediate;


lets rename the parameter file , both the files, the location is the value shown in the `show parameter pfile;`

we are renaming the file to show that if we change initial parameter file, than it wont go on nomount mode

	SQL> startup nomount;

<br>

this means it didn't get the parameter file specified as we have changed the file name, 
lets rename the filename to previous state

	SQL> select status from v$instance;

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i>
To know the name of **control file** (Control file is the heart of database)

	SQL> select name from v$controlfile;

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i>
Change to mount mode

	SQL> alter database mount; 

<br>

after altering the database mount, now we can see the control file is mounted


<i class="fa fa-check-square-o" aria-hidden="true"></i>
To show the mount status:

	SQL> select status from v$instance;

<br>
<i class="fa fa-check-square-o" aria-hidden="true"></i>
Change database to open mode:

	SQL>  alter database open;


<br>
<i class="fa fa-check-square-o" aria-hidden="true"></i>
 Checking the database status:

	SQL> select status from v$instance;

<br>

we can see the status as `OPEN`

<hr>

## Multiplexing in Oracle##

<br>

We are doing multplexing by using the spfile.

<i class="fa fa-check-square-o" aria-hidden="true"></i> Show/describe the number of column in controlfile

	desc v$controlfile;

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> List the control files and their location

	select name from v$controlfile;



<br><i class="fa fa-check-square-o" aria-hidden="true"></i>

	Alter system set control_files=’C:\APP\DBA\ORADATA\ORCL\CONTROL01.CTL’,’C:\APP\DBA\ORADATA\ORCL\CONTROL02.CTL’, ’E:\multiplexing\CONTROL03.CTL’ Scope=spfile;

<br>

here we are creating new control file one in location of previous control file location and another in different drive.

I made a new folder `multiplexing` in E drive so the new control file is in E:\multiplexing

After altering the set of control files, lets shutdown

	shutdown immediate;

<br>

the role of spfile is seen when starting the system


<i class="fa fa-check-square-o" aria-hidden="true"> Copy our control file to our new location</i> in E drive

	host copy C:\APP\DBA\ORADATA\ORCL\CONTROL01.CTL  D:\multiplexing\CONTROL03.CTL

<br>

Here, we are copying from C drive CONTROL01.CTL file to E drive's CONTROL03.CTL file

if there was only one control file present in the system, then we can similarly copy to make CONTROL02.CTL file

lets startup our system,

	startup;

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> Next thing what we are going to do is create pfile from spfile

	create pfile from spfile;

<br>

after creating pfile from spfile, now we are backing up our controlfiles, backup is necessary for databases, when one controlfile fails, we can restore from other.

lets check our work by

	select name from v$controlfile;

<br>

This lists our control file which are in different drives.

<br>
<hr>



## Backing Up Control Files##

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> Control Files are backed up with 

	alter database backup controlfile to trace;

<br>

the backup will be in ASCII format, where as the original control file will be in binary form.


<i class="fa fa-check-square-o" aria-hidden="true"></i> Get the location/contents of control file:

	select value from v$diag_info where name='Diag Trace';

<br>

- the alert file will have log of everything

- scrolling at the bottom we will find the trace file/ back up file with `.trc` extension

- lets open the file

- this trace file will have instruction for creating manually the controlfile

<i class="fa fa-check-square-o" aria-hidden="true"></i> Save the file in the location of multiplexing folder(another drive than C where we created new control file) with new name and type all files.

check the status with

	select status from v$instance;

<br>

if it is open, shutdown

	shutdown immediate;

<br>

- now lets open the control file locations and rename them.

we assume there is no control file in our system by renaming all the control files, in my case there are three control files , you can list the control files with their location by
	
	select name from v$controlfile;

<br>	

We are doing this just to see the effect when there is no control file.


after renaming, to see the effect, do

	startup nomount;

<br>

it won't find/show control files as they have been modified or removed

In such case we need to restore control files.

<br>



## Restoring Control Files##


<br>
<i class="fa fa-check-square-o" aria-hidden="true"></i>  Restore the control files and change to OPEN state by 
	
	@f:\multiplexing\create_ctlfile.sql

<br>

this is the location of the .trc file we just saved in our F drive

this will restore our original control files, previously we renamed them assuming the files are lost, lets see there will be the original control files restored.


	select name from v$controlfile;

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> Check status

	select status from v$instance;



## Viewing Control File Names and Locations##

<br>
if our database is in : **nomount/mount/open** stage we can

<i class="fa fa-check-square-o" aria-hidden="true"></i> View location and name of the control files' location with:

	show parameter control_files;

<br>
<hr>


## Redo Log File##

- important for recovery
- logwriter LGWR writes in log file
- more than one group
- fills next group after filling first, and fills in circular fashion
- overrides first after writing last

Two modes: archive(before overididng, writes from archiver process, no data loss) and non archive

 
<i class="fa fa-check-square-o" aria-hidden="true"> Show the number of logfile

	desc v$logfile;

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> List all gorups, redo log files and their members

	select group#, member from v$logile;

<br>

we can keep copy of each redo logfile by multiplexing.

<i class="fa fa-check-square-o" aria-hidden="true"></i> Show the status of logfile

	select group#,status,members from v$log;
	
<br>

<i class="fa fa-television" aria-hidden="true"></i> output:

	    GROUP# STATUS              MEMBERS
		------ ---------------- ----------
	         1 CURRENT                   1
	         2 INACTIVE                  1

<br>

here, the redo log file is writing to group 1 logfile.

Status explained

- **INACTIVE**: redo logfile doesn't use for instance recovery

- **ACTIVE**: previous logfile where log was written

- **CURRENT**: the file currently being written
<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> Forcefully switch from one log to other

	alter system switch logfile;

<br>
	

After doing this, we can check again by 

	select group#,status,members from v$log;

in my case the group 1 is set to active and 2 to current.

<i class="fa fa-television" aria-hidden="true"></i> output

	GROUP# STATUS              MEMBERS
	------ ---------------- ----------
	     1 ACTIVE                    1
	     2 CURRENT                   1

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> Add a new logfile by multpliplexing

	alter database add logfile member 'C:\ORACLEXE\APP\ORACLE\FAST_RECOVERY_ARE
	A\XE\ONLINELOG\01_MF_1_DG0QXZPK_01.LOG' to group 1;

<i class="fa fa-television" aria-hidden="true"></i> Output

	Database altered.

I just renamed my previous logfile by appending _01

Oracle recommends to place each redo file in different drives and similarly the multiplexed file.


<br><br>

## Dropping a Logfile##


<br>
<i class="fa fa-check-square-o" aria-hidden="true"></i>Logfiles can be dropped by `drop` command

we are dropping the previous logfile we created

	alter database drop logfile member 'C:\ORACLEXE\APP\ORACLE\FAST_RECOVERY_AR
	EA\XE\ONLINELOG\01_MF_1_DG0QXZPK_01.LOG'


After dropping the logfile, we need to delete it physically for erasing permanently. 

<br>
<hr><br>

## Adding a New Redo Logfile Group in Oracle 11g database##

	

first lets find the location of our existing logfiles with

	select member from v$logfile;

<i class="fa fa-television" aria-hidden="true"></i> output

	MEMBER
	----------------------------------------------------

	C:\ORACLEXE\APP\ORACLE\FAST_RECOVERY_AREA\XE\ONLINELOG\O1_MF_1_DG0QXZPK_.LOG
	C:\ORACLEXE\APP\ORACLE\FAST_RECOVERY_AREA\XE\ONLINELOG\O1_MF_2_DG0QY303_.LOG

<br>
<i class="fa fa-check-square-o" aria-hidden="true"></i>Add a new Redo Logfile Group

	alter database add logfile group 4 'C:\ORACLEXE\APP\ORACLE\FAST_RECOVERY_AREA\XE\ONLINELOG\O1_MF_1_DG0QXZPK_02.LOG' size 50M;


<br>

Here, the size is 50MB.

Now, we can verify with: 

	select group#, members, status from v$log;

<i class="fa fa-television" aria-hidden="true"></i> output

	   GROUP#    MEMBERS STATUS
	-------- ---------- ------------
	        1          1 INACTIVE
	        2          1 CURRENT
	        4          1 UNUSED

we can alter the status with 

	alter system switch logfile;

and if we redo 

	select group#, members, status from v$log;

<i class="fa fa-television" aria-hidden="true"></i> output

	 GROUP#    MEMBERS STATUS
	------- ---------- ---------
	      1          1 INACTIVE
	      2          1 ACTIVE
	      4          1 CURRENT


Group 4 is in Current status.


<br>
## Dropping Group##

- possible in inactive state only
- I am trying to drop group 4, so lets switch the group with  `alter system switch logfile;`


until group 4, is in inactive stage, lets keep altering.


<i class="fa fa-television" aria-hidden="true"></i> output

	  GROUP#    MEMBERS STATUS
	------ ---------- -------------
	       1          1 INACTIVE
	       2          1 CURRENT
	       4          1 INACTIVE

<br>

<i class="fa fa-check-square-o" aria-hidden="true"></i> Dropping group

	 alter database drop logfile group 4;

now there are only two groups left.


<br>


**useful commands**

<i class="fa fa-check-square-o" aria-hidden="true"> Show size and details about the logfile

	select * from v$log;

<br>

	select bytes, status, members from v$log;

<i class="fa fa-television" aria-hidden="true"></i> output
	
	BYTES STATUS              MEMBERS
	------ ---------------- ----------
	52428800 INACTIVE                  1
	52428800 CURRENT                   1

<br>


## Resizing Logfiles##

- You cannot resize logfiles. 
- If you want to resize a logfile create a new logfile group with the new size and subsequently drop the old logfile group.

<br>

## Renaming or Relocating Logfiles in Oracle 11g##

To Rename or Relocate Logfiles perform the following steps

For Example, suppose we want to move a logfile from `C:\APP\DBA\ORADATA\ORCL\REDO01.LOG` to `D:\multiplexing\REDO01.LOG`, then this is achived by:

<i class="fa fa-check-square-o" aria-hidden="true"></i> Steps to rename/relocate logfiles:

<i class="fa fa-caret-right" aria-hidden="true"></i>
Shutdown the database

	shutdown immediate; 

<i class="fa fa-caret-right" aria-hidden="true"></i>
Move the logfile from Old location to new location using operating system command

	host move C:\APP\DBA\ORADATA\ORCL\REDO01.LOG  D:\multiplexing\REDO01.LOG

<i class="fa fa-caret-right" aria-hidden="true"></i>
Start and mount the database

	startup mount

<i class="fa fa-caret-right" aria-hidden="true"></i>
Now give the following command to change the location in controlfile

	alter database rename file 'C:\APP\DBA\ORADATA\ORCL\REDO01.LOG' to 'D:\multiplexing\REDO01.LOG';

<i class="fa fa-caret-right" aria-hidden="true"></i>
Open the database

	alter database open;

<hr>

last updated on Tuesday, April 11, 2017







