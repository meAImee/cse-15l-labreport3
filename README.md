# cse-15l-labreport3
## **Find** Command Line Options

---
### Option 1-- **[-mount]**
**[-mount]** Don't descend directories on other filesystems. An alternate name for -xdev. This option is provided **for compatibility with some other versions of find.**

**Example 1**

Command:

`$ find 911report -mount`

Output:

```
911report
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-3.txt
911report/chapter-2.txt
911report/chapter-1.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
911report/chapter-12.txt
911report/chapter-10.txt
911report/chapter-11.txt
```

This returns the list of all files in a specific directory **911report**.
**[-mount]** avoid listing files in other directories.


**Example 2**

Command:

`$ find government/Post_Rate_Comm -mount`

Output:

```
government/Post_Rate_Comm
government/Post_Rate_Comm/Gleiman_EMASpeech.txt
government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
government/Post_Rate_Comm/Mitchell_RMVancouver.txt
government/Post_Rate_Comm/Gleiman_gca2000.txt
government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
government/Post_Rate_Comm/Redacted_Study.txt
government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
government/Post_Rate_Comm/Cohenetal_comparison.txt
government/Post_Rate_Comm/Cohenetal_Scale.txt
government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
government/Post_Rate_Comm/ReportToCongress2002WEB.txt
government/Post_Rate_Comm/WolakSpeech_usps.txt
```

This returns the list of all files in a specific directory **government/Post_Rate_Comm**.

**Example 3**

Command: 

`$ find government/Alcohol_Problems -mount`

Output:
```
government/Alcohol_Problems
government/Alcohol_Problems/Session2-PDF.txt
government/Alcohol_Problems/Session3-PDF.txt
government/Alcohol_Problems/DraftRecom-PDF.txt
government/Alcohol_Problems/Session4-PDF.txt
```

This returns the list of all files in a specific directory **government/Alcohol_Problems**.

This option is usful when we want to search files in a specific directory.








---
### Option 2-- **[-empty]**
**[-empty]** Returns true if a file is empty (contains nothing) and is either a regular file or a directory.


**Example 1**

Command:

`$ find 911report -empty `

Output:

```
```
This returns nothing because no file in 911report is empty.

**Example 2**

Command:

`$ find government -empty `

Output:

```
```
This returns nothing because no file in 911report is empty.

**Example 3**

Command:

`$ find biomed -empty `

Output:

```
```
This returns nothing because no file in 911report is empty.

**This option might be useful when we need to find empty/unedited/useless files in a directory.**


In the directory given for lab3 there is no files that is empty thus testing find-mount in any directory would not return anything.
However, the find -empty command wwould be especially helpful in the future when we need to find the files that are empty/ the files that has been created by mistake and did not have any contents in it.



---
### Option 3-- **[-type]**

**[-type]** Returns files in a directory that has a specific file type:
- b: block (buffered) special files
- c: character (unbuffered) special files
- d: directory
- p: named pipes FIFOs (first in first out)
- f: regular files
- I: symbolic links. This is never true if the -L option or the -follow option was specified, unless the symbolic link is broken. If you want to search for symbolic links when -L is in effect, use -xtype.
- s: sockets
- D: doors (a Solaris file type)

**Example 1**

Command:

`$ find government -type d`

Output:

```
government
government/About_LSC
government/Env_Prot_Agen
government/Alcohol_Problems
government/Gen_Account_Office
government/Post_Rate_Comm
government/Media
```

This command returns all files of type **directory** in directory **government**.

**Example 2**

Command:

`$ find 911report -type c`

Output:

```
```
This command returns nothing because there is no file of type **c(character special file)** in directory **911report**.


**Example 3**

Command:

`$ find plos -type p`

Output:

```
```
This command returns nothing because there is no file of type **p(named pipe file)** in directory **plos**.


**This option might be especially usefl when we need to find files of specific types in directories.**








