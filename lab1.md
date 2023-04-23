# **LAB REPORT 1**
Hello everyone, welcome to CSE 15L. This lab report mainly covers the procedure for installing VS Code, remote connecting and trying some new commands.
## **Installing VS Code**
To install VS Code, I visited the Visual Studio Code website [Link](https://code.visualstudio.com/) , and followed the instructions to download and install it on my computer. 
![Image](Screenshot (15).png)
I downloaded the Windows version for my laptop. When it was installed, it showed a window that looked like this:
![Image](Screenshot (16).png)
## **Remotely Connecting**
First of all, I found my course specific account and reset the password. Then, I tried remotely connecting to the ieng6 server. I started by running a ssh command on the terminal.

`$ ssh cs15lsp23gb@ieng6.ucsd.edu`

It led me to the following prompt where the system asked me to confirm my decision to connect to the server as I was connecting to it for the first time.

`The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?`

I responded 'yes' to the prompt after which I was prompted to input a password (the one that I set before) after which I gained access to the server. It looked like this on the terminal.
![Image](Screenshot (17).png)
## **Run Some Commands**
After gaining access to the server, I got to run commands on the terminal. The commands gave me information regarding the directory I was in. A couple of commands didnot give output. This was because these commands changed the directory I was in and didnot produce any output. The commands given below produced outputs:

`ls -lat`

`ls -a`

`echo` : The echo command is used to display a line of text that is passed in as an argument. This is a bash command that is mostly used in shell scripts to output status to the screen or to a file.

`grep` : The grep command searches the given files for lines containing a match to a given pattern list. In other words, use the grep command to search phrases, numbers, data or strings in a text file.

![Image](Screenshot (18).png)

