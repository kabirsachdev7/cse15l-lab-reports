### 1. Log into ieng6

<img width="708" alt="image" src="https://user-images.githubusercontent.com/114371214/221440557-2c9396cb-e90a-4a8c-a7bc-820a3301a90d.png">

Keys pressed: `<CTRL + R>, <Up>, <Up>, <Up>, <Enter>`
  
I used CTRL + R to search for `ssh` with my login details and it was 3 up in my search history so I used to up arrow to access it and pressed "Enter."

---

### 2. Clone your fork of the repository from your Github account
![image](https://user-images.githubusercontent.com/114371214/221444922-5aeddc66-5b92-4dd8-8d95-9fdf8c2977a8.png)


I typed  `git clone` and used `<CTRL + R>` to search for "github" and then pressed `<enter>`.

Keys Pressed: `<CTRL + R>, <ENTER>`


---


### 3. Run the tests, demonstrating that they fail





Keys pressed: `<Up>, <Up>, <Up>, <Up>, <Up>, <Enter>, <Up>, <Enter>`

I used the up arrow keys 5 times and then pressed enter to get the ` javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` to run the test, as it was previously in my Bash history. I also used the arrow key Up one more time to get `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` and then clicked `<Enter>` to run the Junit Tests. 



---



### 4. Edit the code file to fix the failing test


First I typed `nano <name of the code file>` and pressed `<Enter>`.
Keys Pressed:
- Ctrl + W to search for the failing test.
- Shift + Arrow Keys to select the code that needs to be edited.
- Ctrl + X to cut the selected text.
- Ctrl + V to paste the edited code.
- Ctrl + O to save the changes.
- Ctrl + X to exit nano
  

---

  

### 5. Run the tests, demonstrating that they now succeed

Keys pressed: `<Up>, <Enter>, <Up>, <Enter>

I pushed the up arrow to access the previous `javac` command from the history and then subsequently pressed `<Enter>` to compile the tests. Similarly, to execute, I used the up arrow to access the previous `java` command from history and pressed `<Enter>` to run the `java` command. 

   
---
  
  
### 6. Commit and push the resulting change to your Github account (you can pick any commit message!)
Typed `git add` and then used CTRL + R to search for ListExamples.java and then pressed `<Enter>`
Typed `git commit -m "Fix failing test"` and then pressed Enter
Typed git push origin <


---


