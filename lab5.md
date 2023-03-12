
# Lab Report 5

When reflecting back on the quarter, one of the assignments I really enjoyed was Lab Report 3, where I had the opportunity to select a command of my choice and dig further into how it can be applied in different scenarios and why its so useful. In that report, I gained a deeper understanding of the `grep` command and was hoping to further expand my knowledge on another command such as `touch`, which is used to create blank/empty files and ability to update the timestamp of existing file. Even though it is a simple command, I was intrigued by its vast applicability in different situations, such as its use in shell scripts and other automated processes to create or modify files. 

---

## Researching Commands: Touch

---

### 1. Creating multiple files with a prefix

**Example 1.1: Using a for loop**

Sometimes we might want to create multiple files with a similar name and add a prefix to all of them. The touch command can be used in combination with the echo command and the redirect operator `>` to create multiple files with a prefix. For example, to create three files with a prefix "file_" and the suffix ".txt", I can use the following command:
`for i in {1..3}; do touch file_"$i".txt; done`

**Example 1.2: Using brace expansion:**

Another way to create multiple files with a prefix is to use brace expansion. For example, to create three files with the prefix "javaserver" and the suffix ".txt", I can use the following command:
`touch javaserver{1..3}.java`

This will create three files named "javaserver1.java", "javaserver2.java", and "javaserver3.java".

---


### 2. Using touch to create empty files:
The -n option in grep is used to print the line number along with the matched pattern and is useful when you want to know the exact line number where a pattern occurs in a file.

**Example 1: Searching for the line number for the word "century" in the file "HandRHawaii.txt"**
```
grep -n "century" written_2/travel_guides/berlitz1/HandRHawaii.txt 
44:        and refurbished for the new century, the venerable Kahala artfully
```

The example above shows that the word "century" in HandRHawaii is found on line 44 of the file.

**Example 2: Searching for the line number for the word "history" in the file "Algarve-History.txt"**
```
grep -n "history"  written_2/travel_guides/berlitz2/Algarve-History.txt 
22:To protect its seagoing interests and trade routes, Portugal established strategic garrisons in Goa (India), Malacca (East Indies), and Hormuz in the Persian Gulf. Portuguese explorers then embarked upon Macau (now Macao), the Congo, and various other parts of Africa, including the Sudan. The Portuguese policy was to avoid armed strife and to develop a trade empire, rather than to conquer nations. To this end it succeeded with relatively few blood-soaked episodes in its colonial history.
```
The example above shows that the word "history" in Algarve-History.txt is found on line 22 of the file.

Source: https://www.geeksforgeeks.org/grep-command-in-unix-linux-with-examples/


---

### 3. Using touch to set specific timestamps: 

**Example 1: Searches for the pattern "century" in the file Algarve-History.txt and highlights the matches in color.**

```
grep --color=auto "century"  written_2/travel_guides/berlitz2/Algarve-History.txt 

```
<img width="972" alt="image" src="https://user-images.githubusercontent.com/114371214/218623828-ecdb3806-e10b-412f-8b03-392f7f079ae3.png">


**Example 2: Searches for the pattern "a" in the file Bahamas-WhereToGo.txt and highlights the matches in color..**
```
grep --color=auto "a"  written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt

```
<img width="970" alt="image" src="https://user-images.githubusercontent.com/114371214/218623771-1ebb9a6b-d38f-4be1-a959-41f153ce86a0.png">

The letter "a" in each matching line is highlighted in color, which makes it easier to see where the matches occur in the line. Note that the --color=auto option tells grep to use color highlighting only when the output is sent to a terminal, and not when the output is redirected to a file or a pipeline.


Source: https://man7.org/linux/man-pages/man1/grep.1.html

---





### 4. Using touch to change the file's timestamp without modifying its content:
This command line is useful when searching for all lines that do not match a certain pattern or exclude certain lines from a search.

**Example 1: Search for all the lines in a file named "HandRHawaii.txt" located in the current directory that do not contain the word "century".**
```
grep -v "century" written_2/travel_guides/berlitz1/HandRHawaii.txt 

        Oahu (Including Honolulu)
        Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
        96815; Tel. (808) 922-2700 or (800) 336-5599; fax (808) 922-8785;
        <www.aston-hotels.com>. One of Aston’s many condominium resort
        properties, this modern high-rise has large rooms with complete
        kitchens. Lanais afford views of the Diamond Head end of Waikiki Beach.
        410 rooms.
```
The example above shows the use of -v which returns all the lines in the file that do **not** contain the word "art." To note, the output shown above is a minimal snippet of the overall code. 

Example 2: Search for all files in the current directory that do not contain the pattern "century".
```
grep -v "century" written_2/travel_guides/berlitz2/Athens-Intro.txt 


Athens and
The Athenians
The most important city in the world during its heyday in the fifth and fourth centuries b.c., the people of Athens were highly sophisticated in their thoughts and actions, their tastes and fashions. This small city set on and around a dramatic hill of rock — the Acropolis — became the cradle of western civilization. From the public meetings held here the concepts of citizenship, democracy, and debate developed. 
...
However, since joining the European Union (then the Common Market) in 1981, Greece has definitely moved closer to her western cousins, being one of the first wave of countries to join the Euro currency zone. The government in Athens has done well out of her union, receiving billions of dollars in aid, which has been used to upgrade vital road links throughout the country. Though the economy is still troubled, you are just as likely to see mobile phones as worry beads in a man’s hand, and the young wear the latest European fashions just as the Italians and French do. 
```

The command grep -v "century" written_2/travel_guides/berlitz2/Athens-Intro.txt searches for all lines in the file Athens-Intro.txt located in the written_2/travel_guides/berlitz2 directory that do not contain the word "century", and displays those lines in the terminal.

Source: https://www.tecmint.com/18-important-examples-of-grep-command-in-linux/
