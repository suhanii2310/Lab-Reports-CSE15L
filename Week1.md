# Week1 Lab Report
## Step 1- Installing VSCode

- In order to install VSCode on your device, click on the link below to go to the Visual Studio Code website and select **Download** to install VSCode. (I did not go through this step since I already had VSCode installed on my device)

[VSCodeWebsite](https://code.visualstudio.com/)

![9EDC8CEA-62AD-45F6-9126-0B33CA0B22E0](https://user-images.githubusercontent.com/122580828/212518993-c888b33f-e6b0-4b63-b97f-830d7afd113b.jpeg)


- Select the version suitable for your operating system
- After installation the VSCode window should look like this

![885BF598-E985-42FB-B2D2-83A6BD4CB3CE](https://user-images.githubusercontent.com/122580828/212518279-f6ad364e-f2d2-4f37-853e-ff2ba15388bd.jpeg)



---
## Step 2-Remotely Connecting
- For this step, I first checked if I had **git** installed on my device.To do this we first open the terminal and type "git --version".
- If it results in an error then we need to install **git**
- After installing git we will use the ssh command to connect it to the server.
- Type the following command in the terminal.
-     `ssh cs15lwi23zz@ieng6.ucsd.edu`
-  `ssh` switches the terminal's context to running commands on another computer.
- We have to replace "zz" by our course-specific account. For me it was "awl".
- It will ask you if you want to continue, type `yes`.
- After running this command you will observe that you have been logged into the server.
- The termainal will ask you to enter your password.
- After entering the password the connnection will be established and something like this should be on your screen.

![31836E5A-23F2-4495-9035-8ACAA2DFE14C](https://user-images.githubusercontent.com/122580828/212518404-2d853179-3237-4781-8e4e-d68fa779295d.jpeg)



---
## Step 3-Trying some commands
- We can run commands like `ls`, `pwd`, `cd` etc.
- The commands have the following usage

1. `cd` - "Change Directory" It is used to switch the current working directoryto the given path.
2. `ls` - "List" used to list the files aand folders of the given path.
3. `pwd` - "Print Working Directory" It is used to display the current working directory.


- When we run these commands- cd changed the directory, ls listed the 120 files, while pwd displayed the current working directory which was "/home/linux/ieng6/cse15lwi23/cse15lwi23awl"
- I ran these commands for which I had the following outputs.

![6FD6A820-2C0B-4690-9FEE-C4D14D21A0DE](https://user-images.githubusercontent.com/122580828/212518457-a6c523be-98ee-48b2-93d0-c6780081ee94.jpeg)

-To log out of the server we can use-
1. Ctrl+D
2. Run the command `exit`.
These commands help the user to exit from the server

