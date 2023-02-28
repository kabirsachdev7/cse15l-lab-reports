# Lab Report 4: 

### 1. Log into ieng6

<img width="708" alt="image" src="https://user-images.githubusercontent.com/114371214/221440557-2c9396cb-e90a-4a8c-a7bc-820a3301a90d.png">

Keys pressed: `<CTRL + R>, <Up>, <Up>, <Up>, <Enter>`
  
I used CTRL + R to search for `ssh` with my login details and it was 3 up in my search history so I used to up arrow to access it and pressed "Enter."

---

### 2. Clone your fork of the repository from your Github account
![image](https://user-images.githubusercontent.com/114371214/221744177-0e642baa-8217-46b8-8b00-cfe95dd73749.png)



I typed  `git clone` and used `<CTRL + R>` to search for "github" and then pressed `<enter>`. Afterwards, I typed "cd and l..`<Tab>`" to change the directory into lab7. 

Keys Pressed: `<CTRL + R>, <ENTER>`


---


### 3. Run the tests, demonstrating that they fail





Keys pressed: `<Up>, <Up>, <Up>, <Up>, <Up>, <Enter>, <Up>, <Enter>`
![image](https://user-images.githubusercontent.com/114371214/221757987-fc55bb0a-0eec-4cc3-a17d-cce04c58f547.png)


I used the up arrow keys 5 times and then pressed enter to get the ` javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` to run the test, as it was previously in my Bash history. I also used the arrow key Up one more time to get `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` and then clicked `<Enter>` to run the Junit Tests. 



---



### 4. Edit the code file to fix the failing test

![image](https://user-images.githubusercontent.com/114371214/221753274-e2c872c7-1594-485e-bd51-acf0340eadc4.png)
![image](https://user-images.githubusercontent.com/114371214/221753307-cba0dcd3-c62c-4892-a727-d54a56233c9d.png)

First I typed `nano <name of the code file>` and pressed `<Enter>`.
Keys Pressed:
- Ctrl + W to search for the failing test.
- Shift + Arrow Keys to select the code that needs to be edited.
- Ctrl + X to cut the selected text.
- Ctrl + V to paste the edited code.
- Ctrl + O to save the changes.
- Ctrl + X to exit nano
  
![image](https://user-images.githubusercontent.com/114371214/221755625-62bd90cf-98c5-4f8a-b724-e7eef089fdc9.png)

---

  

### 5. Run the tests, demonstrating that they now succeed
![image](https://user-images.githubusercontent.com/114371214/221757811-93a6a649-57e2-40a1-8ec1-332360133631.png)


Keys pressed: `<Up>, <Enter>, <Up>, <Enter>`

I pushed the up arrow to access the previous `javac` command from the history and then subsequently pressed `<Enter>` to compile the tests. Similarly, to execute, I used the up arrow to access the previous `java` command from history and pressed `<Enter>` to run the `java` command. 

   
---
  
  
### 6. Commit and push the resulting change to your Github account (you can pick any commit message!)

![image](https://user-images.githubusercontent.com/114371214/221755810-a796e843-4352-4e0d-a3f0-1ec51d65b184.png)


Typed `git add` and then used `<CTRL + R>` to search for ListExamples.java and then pressed `<Enter>`
 
I also typed `git status` to monitor all the changes being made to the file and to track the progress. 

Typed `git commit -m "Fix failing test"` and then pressed `<Enter>`to commit it into the repository

Typed `git push origin <main>` and pressed `<Enter>` to push and save the changes into the repository

