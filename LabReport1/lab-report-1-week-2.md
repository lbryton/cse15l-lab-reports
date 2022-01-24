# Week 2 Lab 1 Report:

Test Links:

[Lab Report 1](lab-report-1-week-2.html)

[Lab Report 1](https://lbryton.github.io/cse15l-lab-reports/LabReport1/lab-report-1-week-2.html)

## **Setting up Visual Studio Code**

> Go to this [*link*](https://code.visualstudio.com/) to download the Visual Studio Code version for your operating system (OSX for Macs and Windows for PCs). This page should appear:
![Image](Part1A.png)
After downloading and installing Visual Studio, open up the application, and you should be prompted with this screen:
![Image](Part1B.png)

## **Remotely Connecting to CSE course-specific accounts**

>To remotely connect to your CSE course-specific account, you will have to go to this [*link*](https://sdacs.ucsd.edu/~icc/index.php). ![Image](Part2A.png)After signing in with your UC San Diego username and PID, you will find your course-specific account under **Additional Accounts**. Your account username may include the specific class and quarter you are taking this class. To use this account, you will have to create a password. When you change your password, make sure you pick only to change the course account. Otherwise, you will also change your passwords for your TritonLink account. ![Image](Part2B.png) After setting up the password for the account, you can now remotely connect to the UC San Diego servers. By typing using the command listed below and then entering the password created, you can connect with the UC San Diego servers.![Image](Part2C.png)

```ssh (account username)@ieng6.ucsd.edu```

## **Running Some Commands**

>After you have remotly connected to the UC San Diego servers, there are a few commands you could try out:
* cd: Used to change your directory.
* ls: Used to list out the files and directories of a specific directory. You can use ls -a, ls -la, and ls -lat to display more information about a specific directory
* pwd: Used to print out the directory the user is at.
* mkdir: Used to create a directory.
* cp: Used to copy files or a directory.
* scp: Used to transfer data between two different systems (Server and Client for example).
* cat: Used to create and view files.
![Image](Part3A.png)

## **Moving Files with *scp***

>One example of the use of scp is transferring files from your computer onto the remote computer. For example, you can copy the file WhereAmI.java with the code below onto the remote computer:
![Image](Part4A.png)
You do this by using the command scp (file name) (account username)@ieng6.ucsd.edu:~/.
![Image](Part4B.png)

## **Setting up an SSH Key**

>You can create a SSH Key to remove the process of typing in your account password everytime. You create your SSH Key by typing in ssh-keygen -t ed25519. You can specify the location of where you would like the keys to be generated and the password for the keys. Make sure you remember your password, as it will be your login password when remotely connecting.
![Image](Part5A.png)

## **Optimizing Remote Running**

>To use your SSH Key for optimizing your remote running, you will have to copy your key onto the directory of your server account. You will have to:
* Create a .ssh directory in your server account (mkdir .ssh)
* Then copy the public SSH Key into that directory from your computer:
scp /Users/(username))/.ssh/id_rsa.pub (account username))@ieng6.ucsd.edu:~/.ssh/authorized_keys
![Image](Part6A.png)
![Image](Part6B.png)