## GitHub Things

#### Making a Repository

*A repository is a place to store code. People can add, change, remove, and use code via repositories.*

1. Click the plus icon at the top right of GitHub page and make a new repository
2. Fill in information such as...
   - Its name (which can be changed later with some effort)
   - A description if you want
   - Whether it is public or private (can make it private until your project is in more organized state)
   - Whether to add a readme (which you probably do want to do)
   - If there is a .gitignore (you can choose from a bunch of templates GitHub has based on which language you are using)
   - And which lisence you will use (can change later)
3. Then click create and you will have a repository

#### Cloning a Repository

*Cloning a repository allows you access the code on your local machine.*

1. Make sure you have an ssh keypair to allow your local machine to access your account (so the public key in your GitHub account and the private key on your machine)
2. Make sure you have git installed on your machine
   for Linux, run this command in the terminal
   > sudo apt install git-all
   for MacOS, run any git command, such as the one below. If git is not installed, you will be prompted to install it
   > git --version
   For Windows, just switch to another operating system
3. Open the terminal and navigate to the directory where you want the project directory to be located
4. Run this command, where [repository page] is the URL like thing copied from the webpage of the repository (click the green "code" dropdown, go to the ssh section, and copy that string of text).
   > git clone [repository page]
5. You have successfully cloned a repository, and can now open your IDE and open the project directory from wherever you saved it to start working on your project.

## Programming Things

### Navigating File Structures via the Terminal

- Running "cd [file path]" allows you to switch to whatever directory was specified in the file path (as "cd" stands for "change directory")
  - These file paths can be relative to the current directory, or absolute paths
- Running "ls" shows you all the items in the current directory
- "." means current directory, and ".." means one directory up
- If you know what you are doing, you can use a file path to get exactly where you need to go
- If you are uncertain of the directories on your computer, you can use "cd [directory]" and "cd .." to go up and down directory levels, then check where you are using "ls", until you find where you need to be
