# Lab Report 1:An Introduction to GitHub Pages
## Step 1: Setting up CSE 15L Account
To setup my account, I began by first using the account lookup using the [Account Look Up Tool](https://sdacs.ucsd.edu/~icc/index.php), to decipher the username of my CSE 15L account. 

<img width="643" alt="Account Lookup Results" src="https://user-images.githubusercontent.com/114371214/212163750-5cc123d1-6286-4a84-910d-1fbd6310bd09.png">

Subsequently, I clicked on the global password account reset button and changed my password for only this course-specific account. Once successfully changing the password for my account, I had to wait approximately 15 minutes for the changes to be registered into the system. 

## Step 2: Installing Visual Studio Code
Once the changes were made, I opened up a new window and terminal in Visual Studio Code. I had the application already downloaded, and thus did not need to take further measures to acquire the application. However, if you do not have it downloaded, go to [Visual Studio Code](https://code.visualstudio.com/) and install it onto your computer. 

<img width="1018" alt="Pasted Graphic 3" src="https://user-images.githubusercontent.com/114371214/212163968-898a37b8-bd34-47c8-abc2-76291928e1da.png">

## Step 3: Remotely Connecting using SSH 
The account lookup allowed me to find out my username so I then wrote this line of code into the terminal: **$ ssh cs15lwi23aqo@ieng6.ucsd.edu** and put in my password. You would simply need to change the username to your own account name and then keep the address as **@ieng6.ucsd.edu**. For reference: *ACCOUNTNAME*@ieng6.ucsd.edu.

<img width="694" alt="TERMINAL" src="https://user-images.githubusercontent.com/114371214/212164484-25f38ac6-dcb8-4fb4-bed3-09b05fbf56c8.png">

When successfully logged in, I was prompted with a message indicating that the terminal is now connected with a computer in the CSE Basement. 

![UcDfuBRzXNTMLtu9tWVXKuvF43SYq7yrkCCVU8u9g7WE2gcH4CyEN3VUpuD9EOaLMB9SsmvWw6Fz7lQ-1AAOf6Eb1fHyL9Bdxg8QQURajsjrjwmAt26yYOPo-xhn](https://user-images.githubusercontent.com/114371214/212164530-4d196a4d-f333-4759-991a-d3503e944671.png)

## Step 4: Running Commands into the Terminal
I proceeded to list out some commands into the terminal to examine different error messages, and what information is being outputted. You can try different linux commands such as these:

<img width="648" alt="group members' username" src="https://user-images.githubusercontent.com/114371214/212164654-2480596b-6178-48c8-8257-2553feeea71d.png">

cd ~ - --> changes the current directory to the home directory of the current user. ~ is a shorthand for the home directory.

cd --> changes the current directory to the home directory of the current user without arguments.

ls -lat --> lists the contents of the current directory in long format (-l), showing details such as permissions, owner, size, and modification time. The contents are sorted by modification time, with the newest items first (-t).

ls -a --> lists the contents of the current directory, including hidden files and directories (-a).

ls <directory> --> lists the contents of the specified directory. In the example ls /home/linux/ieng6/cs15lwi23/cs15lwi23abc, the <directory> argument is /home/linux/ieng6/cs15lwi23/cs15lwi23abc.

cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/ --> copies the file /home/linux/ieng6/cs15lwi23/public/hello.txt to the home directory of the current user.

cat /home/linux/ieng6/cs15lwi23/public/hello.txt --> displays the contents of the file /home/linux/ieng6/cs15lwi23/public/hello.txt to the terminal. cat is short for "concatenate" and is often used to display the contents of text files.

## Step 5: Constructing a Github Page
<img width="1356" alt="Pasted Graphic 7" src="https://user-images.githubusercontent.com/114371214/212164705-ce611bee-f8fb-4d24-aedc-6dcbb604b93e.png">

Lastly, I proceeded to [Github](github.com), and since I had an account already registered I did not need to make another one. However, if you do not have an account, simply register on their website. 

## Step 5: Creating a repository on Github 
On the Github site, I created a new Repository titled *cse15l-lab-reports* and left the settings on the repository to the default settings already in place. To create a new repository, simply click on the **+** beside your profile picture on the top write and there will be a dropdown that provides you with the option to create a *new repository*. With my new repository, I created a new file called **index.md** which is a markdown file and then committed it into the repository. I also modified the *Pages* settings to make the branch source as **main**.

<img width="1176" alt="Pasted Graphic 8" src="https://user-images.githubusercontent.com/114371214/212164841-6ce1044a-4069-4f67-9d0a-61d15a99b96a.png">

On the top of the **Pages**, you can also see that it is able to Visit the site of the new created repository as well. The message *“your site is live at”* allows us to click on the link and view the page in its entirety. 

