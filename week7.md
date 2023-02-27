# Week 7 Lab Report

## Step 1 - Setup Delete any existing forks of the repository you have on your account

To delete any existing forks of the repository "lab7" you should go the the repository and click on the settings menu. Scrolling down on the page you will see a dangerZone where oyu can delete that particular repository.
![9519ABAD-6CA4-4558-A09E-72C5B2419DC0](https://user-images.githubusercontent.com/122580828/221464484-a04e9793-f4d1-4735-bcb8-cbcd42b36174.jpeg)

![28BF07AB-2ABB-409D-8098-A0FFBAF249BB](https://user-images.githubusercontent.com/122580828/221464488-16dd88d9-3ec5-490e-85fb-99e9e8640f4c.jpeg)

![A5084790-6888-4CC8-B9D4-45AA1209CDB2](https://user-images.githubusercontent.com/122580828/221464493-ab543481-da83-4d34-a34e-93ab4deead26.jpeg)


## Step 2 - Setup Fork the repository

 We can fork the repository by clicking on fork on the upper right side of the page.
 
![3F6D6E1D-ECBB-48C7-8103-C34AB8E5E49B](https://user-images.githubusercontent.com/122580828/221464640-7a929bc8-e2d0-4522-95b4-620b27bb2f82.jpeg)


## Step 3 - The real deal Start the timer!

Start the timer now to time yourself doing the rest of the steps.

## Step 4 - Log into ieng6

Since I had already setup the github and login command line setup the terminal doesn't ask for my password when i login with `ssh cs15lwi23awl@ieng6@ucsd.edu` 

![37336A86-296C-47B6-BD44-72D8EEC95605](https://user-images.githubusercontent.com/122580828/221469681-17588010-44d0-44b2-9b5c-fa9a58bb220a.jpeg)



## Step 5 Clone your fork of the repository from your Github account

To clone the repository from a github account we have to click on `<> Code` and then copy the ssh key url.

![BA016665-79F2-4A52-91B0-4117FEA6D17B](https://user-images.githubusercontent.com/122580828/221471816-23361b35-3007-475c-82f2-0d7814728409.jpeg)


In the terminal run the command `git clone <copied ssh url>`. This should clone the repository form your github account.

![F8888C0E-18AC-4B19-B24B-507127DD8E12_4_5005_c](https://user-images.githubusercontent.com/122580828/221469743-35629bf4-2398-4147-a4b2-953e8c8d3c5b.jpeg)




## Step 6 Run the tests, demonstrating that they fail

- To run the tests, we first change the directory to lab7 which has the files "ListExamples.java" and ListExamplesTests.java".
- We complile the fie using `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`.
- To run the tests we use `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`.
- We observe that one out of two tests fail. The test that failed was "testMerge2" indicating a problem with the method "merge(List<String> list1, List<String> list2)".
  

![0760EA8B-A4B7-4DD5-997D-929ED1799441](https://user-images.githubusercontent.com/122580828/221469792-b8c7412a-b016-4161-b5e3-427278cbabfb.jpeg)


## Step 7 Edit the code file to fix the failing test
  
 - To edit the code file we use the command ` nano `.
 - We use `nano ListExamples.java` to edit the method.

![6BA65141-5F9A-47D5-82B5-A0B2509222A8_4_5005_c](https://user-images.githubusercontent.com/122580828/221470231-94d2e913-bec6-4710-b789-ae099dc0822d.jpeg)

- The code file opend and now we can edit the code so that we pass all the tests.
- We go down to the 43rd line of the file.
Keys pressed(<down> 42 times): <down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down>down><down>
 
![04BFE16E-AA01-46B0-857D-FF82ACF6B00B](https://user-images.githubusercontent.com/122580828/221470054-5cdf102e-ba3a-46cb-825e-de89a50ca34c.jpeg)

- Then we go 12 spaces right in the 43rd line.
 Keys pressed(<right> 12 times): <right><right><right><right><right><right><right><right><right><right><right><right>

![3BA47152-85B1-406D-B364-AC1576A3550F](https://user-images.githubusercontent.com/122580828/221470043-e1e0531d-3b10-4f67-84ed-6b9ca32dac7c.jpeg)

- We change the "index1" to "index2". We make this change because the code was not updating the index value of the second list.
Keys pressed : <delete><2>
 
![EB3A9C6D-31D2-491E-8A23-DA147D7937E3](https://user-images.githubusercontent.com/122580828/221470064-ca114f69-d0d4-42ac-81a2-0846455caf3e.jpeg)

- To save this change we press <control>+<o> and the press <enter>.

![7DF2E732-3F3B-4182-961B-CF92F30B0C8C](https://user-images.githubusercontent.com/122580828/221470077-964765d4-9734-4c46-9e54-57bbed45701b.jpeg)

- To exit press <control>+<x>.
 
![BE4EC164-E31D-4E42-9D7E-DBEEDF7ABF55](https://user-images.githubusercontent.com/122580828/221470086-fbc6b8c4-e9b2-4990-bf42-747f1e0162a9.jpeg)



## Step 8 Run the tests, demonstrating that they now succeed

- To compile the code we use `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command which was 3 up in the search history, so I used up arrow to access it.
 Keys pressed: <up><up><up><enter>
- To run the code we use `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` command which was 3 up in th esearch histpry, so I used up arrow to access it.
 Keys pressed: <up><up><up><enter>
- we observe that the code passes all the tests now.

![33AC321F-EB0C-4424-8B5F-7B7D036EA9EE](https://user-images.githubusercontent.com/122580828/221470093-e08af5bd-d8b3-4eb9-b702-dac88d454e4e.jpeg)


## Step 9 Commit and push the resulting change to your Github account (you can pick any commit message!)
 
- To commit and push the changes made we use the following commands.
- `git add .`
- `git commit -m "commit message"`
- `git push`

![80A346C9-CF5E-4B80-9F37-7B15D7ABF2CF](https://user-images.githubusercontent.com/122580828/221470114-40dd920b-9eee-4a4b-957f-fc6d086ec6ac.jpeg)








