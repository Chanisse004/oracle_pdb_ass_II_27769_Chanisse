# oracle_pdb_ass_II_27769_Chanisse

# Oracle Pluggable Database Assignment II

## Student Information
- First Name: Chanisse
- Student ID: 27769
- Repository Name: oracle_pdb_ass_II_27769_chanisse


# Overview

This assignment demonstrates the creation, management, and monitoring of Oracle Pluggable Databases (PDBs) using SQL*Plus and Oracle Enterprise Manager (OEM).

## Oracle Environment Used

Oracle Database 21c Express Edition (XE)

SQL*Plus

Windows Command Prompt

Oracle Enterprise Manager (OEM)

The tasks completed include:
- Creating a new PDB following strict naming conventions
- Creating a dedicated user inside the PDB
- Creating and deleting a temporary PDB
- Accessing and verifying the environment using OEM

# Task 1: Create a New Pluggable Database

## PDB Details
- PDB Name: ch_pdb_27769
- Username Inside PDB: chanisse_plsqlauca_27769
- Password: (private for security reasons)

## Steps Performed

1. Connected as SYSDBA using SQL*Plus.
2. Created the PDB using the required naming convention.
3. Opened the PDB in READ WRITE mode.
4. Saved the PDB state to ensure automatic startup.
5. Switched session to the new PDB.
6. Created the required user inside the PDB.
7. Granted necessary privileges to the user.

## Verification

The following commands were used to verify success:
SELECT PDB_NAME, OPEN_MODE FROM V$PDBS;
SHOW CON_NAME;
SELECT USERNAME FROM DBA_USERS;

# Task 2: Create and Delete a Temporary PDB
Temporary PDB Information

 Temporary PDB Name: ch_to_delete_pdb_27769

Steps Performed

Created the temporary PDB.

Verified its existence using:
SELECT PDB_NAME FROM V$PDBS;
Closed the PDB.

Dropped the PDB including datafiles.

Confirmed complete deletion by checking V$PDBS again.

# Task 3: Oracle Enterprise Manager (OEM)
Configuration

Accessed OEM via:
https://localhost:5500/em

Logged in as SYSDBA.

Verified:

Oracle CDB environment

ch_pdb_27769 in READ WRITE mode

User chanisse_plsqlauca_27769 visible inside the PDB

# Challenges Encountered and Solutions
 ORA-01017: Invalid Username/Password

Cause:
Attempted connection from incorrect container.

Solution:

ALTER SESSION SET CONTAINER = ch_pdb_27769;

 PDB Not Visible in OEM

Cause:
PDB was not open in READ WRITE mode.

Solution:

ALTER PLUGGABLE DATABASE ch_pdb_27769 OPEN;
ALTER PLUGGABLE DATABASE ch_pdb_27769 SAVE STATE;


All issues were resolved successfully.

# Integrity Statement

I confirm that this assignment was completed independently using my own Oracle environment.

All commands were executed, verified, and tested personally.

I understand that precision, discipline, and integrity are essential qualities in database administration and commit to maintaining professional and ethical standards in all technical work.


