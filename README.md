# Mainframe

Assignments - 

Assignment 1 - 
Manually create a PS (Physical Sequential) file using ISPF 3.2 option containing 100
records, each 80 bytes in length. The records are structured such that the primary
key is located between columns 13 and 20. Out of the 100 records, 10 are
duplicates, and the remaining 90 are unique. The records are stored in random
order.
Task: Write a JCL SORT to:
a) Eliminate the duplicate records.
b) Sort the remaining records based on the primary key (columns 13-20).


Assignment 2 - 
Create two PS files:
File1: Contains 50 records, each 80 bytes long, with the primary key located in
columns 13 to 20.
File2: Contains 50 records, each 80 bytes long, with the primary key located in
columns 21 to 28.
Task: Write a COBOL program that:
Reads both files (File1 and File2).
Creates a new file, File3, which will contain only the matching records from File1 and
File2, based on the primary key found in both files.


Assignment 3 - 
Create a PS (Physical Sequential) file containing 120 records, each 100 bytes in
length. The records are structured such that the primary key is located between
columns 25 and 32. 
Out of the 120 records, 15 are duplicates, and the remaining 105 are unique. The
records are stored in random order.
Task: Write a REXX program to:
a) Remove the duplicate records.
b) Sort the remaining records based on the primary key (columns 25-32).


Assignment 4 - 
Write a job
a) to copy input PS/PO file into output file using IBM SORT utility in Descending
order
b) compare the total records count before and after sort
c) keep the output file only if step b) is successful otherwise print an error
message
d) Test both scenarios: step b) succeeds and fails
Concepts covered: File handling, data Sort, file Copy, conditional statements


Assignment 5 -
VSAM KSDS Creation and Access
Create a VSAM KSDS (Key-Sequenced Data Set) with the following structure:
Key: Customer ID (columns 1-8)
Data: Customer Name (columns 9-40) and Address (columns 41-100)
Task:
Write a COBOL program to:
Insert 20 customer records into the KSDS file.
Display the records in ascending order based on the Customer ID.
Search for a specific Customer ID provided by the user and display the
corresponding record.


Assignment 6 - 
GDG (Generation Data Group) Management and Archiving
Create a Generation Data Group (GDG) base to store daily transaction logs.
Each generation will contain 100-byte records with the following structure:
Columns 1-10: Transaction ID
Columns 11-30: Transaction Date
Columns 31-100: Transaction Details
Task:
Write a JCL job to:
Add a new generation to the GDG base with 10 sample transactions.
Use the IDCAMS utility to list all the existing generations in the GDG base.
Archive the last 3 generations into a PS file, then delete these generations from the
GDG base.


Assignment 7 -
Understanding on JCL and VSAM.
a) Create a VSAM KSDS file using IDCAMS, in step #1 of a JCL.
b) Use another IDCAMs step to write a pre-loaded PS file in to this KSDS file.
Run LISTCAT on this loaded KSDS dataset and analyze the output.


Assignment 8 - 
Understanding on JCL and GDG
a) Create a GDG base. Keep in mind the GDG max number of generations.
(Read about LIMIT, EMPTY/NOEMPTY, SCRATCH/NOSCRATCH)
b) Write four records to a new generation of this GDG. Keep LRECL=40 bytes.
(Sample record
AAAAAAAAAA1111111111@@@@@@@@@@................
BBBBBBBBBB2222222222@@@@@@@@@@................
CCCCCCCCCC3333333333@@@@@@@@@@................
DDDDDDDDDD4444444444@@@@@@@@@@................
EEEEEEEEEE5555555555@@@@@@@@@@................
And so on…)
c) In another step, write four more records into a new generation of this GDG.
d) Repeat step 2(c).
e) Repeat step 2(c) again.
f) By now, you will have four generation in your GDG base with each having four
records.
g) Write a rexx script or use SORT to concatenate (at record level) GDG(+1) and
GDG(+4) in to a single PS file(LRECL=80, total records=4) and GDG(+2) and
GDG(+3) in to another PS file(LRECL=80 bytes, total records=4).
Final output is two PS files with LRECL=80 bytes and each having four
records. Example below:
GDG(+1).. AAAA1111
GDG(+3).. BBBB2222
PS File output… AAAA1111BBBB2222
