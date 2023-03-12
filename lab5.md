
# Lab Report 5

When reflecting back on the quarter, one of the assignments I really enjoyed was Lab Report 3, where I had the opportunity to select a command of my choice and dig further into how it can be applied in different scenarios and learn about why the command is truly so useful. In that report, I gained a deeper understanding of the `grep` command and was hoping to further expand my knowledge on another command such as `touch`, which is used to create blank/empty files and ability to update the timestamp of existing file. Even though it is a simple command, I was intrigued by its vast applicability in different situations, such as its use in shell scripts and other automated processes to create or modify files. 

---

## Researching Commands: Touch
The touch command can be used to create new files or directories, update the timestamps of existing files or directories, or set the timestamps of files or directories to match those of a reference file. It also has several options that allow you to control the behavior of the command, such as specifying a specific timestamp to set, updating only the access or modification time, or updating the timestamps of all files in a directory.

Learning more about the touch command and its various options can be beneficial for me as I hope to work in software development, or data management where uderstanding how to manipulate file timestamps can help me organize and manage files more effectively, troubleshoot problems, and automate tasks. 


---

### 1. Creating multiple files with a prefix

**Example 1: Using a for loop**

Sometimes we might want to create multiple files with a similar name and add a prefix to all of them. The touch command can be used in combination with the echo command and the redirect operator `>` to create multiple files with a prefix. For example, to create three files with a prefix "file_" and the suffix ".txt", I can use the following command:
`for i in {1..3}; do touch file_"$i".txt; done`

In this command, we're using a for loop to iterate through the values 1 to 3, and for each value, we're using the touch command to create a file with the name "file_" followed by the value of i and the suffix ".txt". The dollar sign ($) is used to access the value of the i variable.



**Example 2: Using brace expansion:**

Another way to create multiple files with a prefix is to use brace expansion. For example, to create three files with the prefix "javaserver" and the suffix ".txt", I can use the following command:
`touch javaserver{1..3}.java`

This will create three files named `javaserver1.java`, `javaserver2.java`, and `javaserver3.java`.

In this command, we're using brace expansion to generate a series of strings with the pattern "javaserver" followed by a number from 1 to 3, and the suffix ".java". The touch command is then used to create files with these names.


Source: https://www.hostinger.com/tutorials/linux-touch-command-with-useful-examples/

---


### 2. -a (access time): Updates only the access time of the file(s) rather than the modification time:
This option changes the access time of the file(s) to the current time, without changing the modification time. Access time is the last time a file was read or written.

**Example 1: Change the access time of a file named "HandRHawaii.txt" to the current time**
```
touch -a written_2/travel_guides/berlitz1/HandRHawaii.txt 
```

This command will update the access time of "HandRHawaii.txt" to the current time without changing its modification time.



**Example 2: Change the access time of all files in a directory named "written_2" to the current time."**
```
touch -a written_2/*
```
This command will update the access time of all files within the "written_2" directory to the current time.


Source: https://linuxize.com/post/how-to-use-linux-touch-command/


---

### 3. -t (or --time): Allows the ability to specify a custom timestamp for a file, instead of using the current time: 
The timestamp should be in the format "[[CC]YY]MMDDhhmm[.ss]" where each bracketed section is optional and represents the year (CC=century, YY=year), month, day, hour, minute, and second.

**Example 1: Set the modification time of a file named "century.txt" to January 1, 2023 at 12:30 PM**

```
$ touch -t 202301011230 written_2/travel_guides/berlitz1/century.txt

```

This command uses the "-t" option to set a custom timestamp for the file "century.txt". The timestamp specified is "202301011230", which represents January 1, 2023, at 12:30 PM. The path to the file is "written_2/travel_guides/berlitz1/century.txt" and after running this command, the modification time of "century.txt" will be set to the specified timestamp.



**Example 2: Set the access time of a directory named "written_2" to August 7, 1997 at 2:30 AM**
```
$ touch -t 199708070230 written_2/

```
This command also uses the "-t" option to set a custom timestamp, this time for the directory "written_2". The timestamp specified is "199708070230", which represents August 7, 1997, at 2:30 AM. Since this command only specifies a directory and not a specific file, the access time for the directory will be updated, but not the modification time. After running this command, the access time of "written_2" will be set to the specified timestamp.


Source: https://shapeshed.com/unix-touch/

---





### 4. -r (or --reference): This option sets the modification and access times of a file to be the same as those of another file specified by a reference file:

This can be useful when you want to synchronize the times of two files or reset the times of a file to a previous state.

**Example 1: Set the modification and access times of a file named "Beijing-History.txt" to be the same as those of a reference file named "Bermuda-WhatToDo.txt".**
```
$ touch -r /written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt /written_2/travel_guides/berlitz2/Beijing-History.txt
```
In this example, we use the touch command with the -r option to set the modification and access times of a file named `Beijing-History.txt`in the `/written_2/travel_guides/berlitz2/`subdirectory to be the same as those of a reference file named `Bermuda-WhatToDo.txt`in the same directory. In this case, we specify the path of the reference file as `written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt` and we specify the target file `Beijing-History.txt ` in the same directory as the last argument.
 

**Example 2: Set the modification and access times of all files in berlitz2 to be the same as those of a reference file named "Bermuda-History.txt".**
```
$ touch -r written_2/travel_guides/berlitz2/Bermuda-History.txt written_2/travel_guides/berlitz2/*
```

In this example, we use the touch command with the -r option to set the modification and access times of all files in the `berlitz2/` subdirectory to be the same as those of the file `Bermuda-History.txt`.

By setting the timestamps of all files in the directory to be the same as the reference file, we can ensure that all the files have consistent timestamps, which can be useful for organizing and managing files.

Source: https://www.tecmint.com/8-pratical-examples-of-linux-touch-command/

---

### 5. -c (or --create): if the file does not exist, do not create it ###

This command is used to update the timestamps of a file only if it already exists. If the file does not exist, nothing happens and the command returns to the command prompt without any output.

**Example 1: Update the timestamps of a file only if it already exists.**
```
touch -c ./written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
```
In this example, we use the -c option with the touch command to update the access and modification times of a file called `Canada-WhereToGo.txt` in the `./written_2/travel_guides/berlitz2/` directory. If the file exists, the timestamps will be updated to the current time; if the file does not exist, nothing happens and the command returns to the command prompt without any output.

**Example 2: Use the -c option with a wildcard to update the timestamps of all existing files in a subdirectory.**
```
touch -c ./written_2/travel_guides/berlitz2/*
```

In this example, we use the -c option with the touch command and a wildcard `*` to update the access and modification times of all existing files in the `./berlitz2/` subdirectory. If a file exists, its timestamps will be updated to the current time; if a file does not exist, nothing happens and the command moves on to the next file. Since files exist, this is a useful way to update the timestamps of all files in a directory without creating new files if they do not already exist.

Source: https://www.tecmint.com/8-pratical-examples-of-linux-touch-command/

