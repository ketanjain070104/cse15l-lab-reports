# **LAB REPORT 4**
This report guides us through cloning a repository and making changes to it using command terminal (vim and git commands).
Note: Steps 1-3 are not covered in this lab report
## Step 4: Logging into ieng6 account

![Image](Screenshot (15).png)

I opened the terminal and typed in ```ssh cs15lsp23gb@ieng6.ucsd.edu```. Then I pressed ```<enter>``` to execute the command. I don't have to put my password anymore because I have configured my account using the SSH keys.

## Step 5: Cloning my fork of the repository from my GitHub account

![Image](Screenshot (15).png)

I used ```<Ctrl-C>``` and ```<Ctrl-V>``` to paste the command ```git clone https://github.com/ucsd-cse15l-s23/lab7``` which clones the repository onto the ieng6 machine.

## Step 6: Demonstrating that the tests fail

![Image](Screenshot (15).png)

I used the ```ls``` command to see all the available directories. Then, I used the ```cd lab7``` command and pressed ```<enter>``` to change directories. I put in the ```pwd``` command to check if I am in the correct directory. Lastly, I used the command ```bash test.sh``` to run the Junit tests for ListExamples.java file.

## Step 7: Editing the code file

![Image](Screenshot (15).png)

I used the command ```vim ListExamples.java``` and pressed ```<enter>```. This changed my terminal to vim in normal mode. I locate the error and use the ```k``` and ```l``` keys to get to the position of the faulty index value. I used ```x``` to delete the 1 in index 1. Then, I pressed ```i``` to enter insert mode. Here, I added 2 by pressing ```<2>``` and then esacped to normal mode by pressing ```<esc>```. I saved the chnages by typing in ```<:wq>``` 

## Step 8: Demonstrating that the tests succeeded

![Image](Screenshot (15).png)

I used the ```<Ctrl-C>``` and ```Ctrl-V``` commands to copy and paste ```javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2 *.java``` and then pressed ```<enter>```. This creates a class file. Then I used the same keys again to copy and paste the ```java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests``` command to run the file.

## Step 9 Commit and Push 

![Image](Screenshot (15).png)

I used the ```git add ListExamples.java``` command to push the changes made to the directory and pressed ```<enter>``` to execute it. I used the ```git commit -m "update"``` command to record changes. I used the ```git push origin``` command to update the local repository content to a remote repository and executed the command by pressing ```<enter>```.
