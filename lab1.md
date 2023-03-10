## Installing VS Code: 
To install VS code go to the following website [Link](https://code.visualstudio.com/) and click the download button.

![](vsCode.png)

* My Laptop already had VS Code installed on it so I did not have to do anything in order to install VS code for this lab.
      
Then choose the correct operating system and click download. 
* My Laptop already had VS Code installed on it so I did not have to do anything in order to install VS code for this lab. 

Once the file is downloaded open the downloaded file and accept the terms and conditions. Then it should begin downloading VS code on your laptop
* My Laptop already had VS Code installed on it so I did not have to do anything in order to install VS code for this lab. 

Once VS code is installed it will display a screen like this:

![](vsCode1.png)

## Remotely Connecting: 
Look up your CSE 15L account using this link [Link](https://sdacs.ucsd.edu/~icc/index.php).
   * Once you click the link it should ask you for your personal school information. 
   * Prove the right information and it will redirect you to your account username. 
   * Make sure to remember or save this username for later steps.

![](lookup.png)
   
Install Git for windows using this link [Link](https://gitforwindows.org/).
   * Click Download. 
   * Once the file is finished downloading open the file and then select the suitable preferences and finish the instalation. 

Open VS Code and change the default terminal in VS code to git-bash.
   * Use the directions in this link ([Link](https://stackoverflow.com/a/50527994)) in order to change the default terminal to git-bash.
   * Remember you can toggle between the different terminals using the dropdown menu.
   * Stay in the Git-Bash terminal for the next steps. 

Connect remotely to the server. 
   * in the new terminal in VS Code from the previous step type in "ssh " followed by your specific username found in the earlier step with a "@ieng6.ucsd.edu" added on to it. 
   * You will likely get a message asking you to confirm if you want to connect to the server if it is the first time connecting. Type Yes in order to proceed with connecting to the server. 
   * You will likely be asked to enter your password and you should enter the one provided by the school in order to finish connecting to the server. 
   
   `Note: The terminal does not show whatever you are typing while entering the password for security reasons`

Once you are finished connecting it should display a message like this:
![](server.png)

## Running Commands: 

Now that you are connected to the server you can run some commands by just typing them into the terminal.
   * Type in whichever command you want to use and click enter and it should execute the command. 
   * For example if you type in "ls -lat" command into the terminal this should be the result. 

![](command.png)

I learnt `ls` method is used to list the files in the directory. The addition of the `-l` makes it so that the files are formatted laterally. The `-a` makes it so that even the hidden files are displayed. The `-t` makes it so that the times and dates of the files are displayed and also used to sort the files. 

Thus the `ls -lat` lists all the files in a lateral format with the hidden files that have dots and the times of the files. 

Some other commands that are useful are:
* `cp`: The cp command copies a file into the home direcotry. 
* `mkdir`: The mkdir command creates a new directory in the current location.
* `pwd`: The pwd command prints the working directory.
* `cd`: The cd command changes the current directory to the given path. 
* `cat`: which displays the files

You can use these commands create new directories to organize files.

"is a directory" is an error that may be generated if you try to perform an operation on a directory that can only be performed on a file so be careful. 

Click Ctrl + D to log out of the connection.
