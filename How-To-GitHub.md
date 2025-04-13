## Git Commands

*See https://education.github.com/git-cheat-sheet-education.pdf for list of commands*

### Pushing Changes to a Repository
- Changes to repositories are done via pull requests, where a programmer requests for their code to be added to the project, and someone else reviews and then hopefully approves the request
- Each pull request has a 'branch' associated with it, and each pull request / branch should contain changes centered around some goal (not a bunch of random small goals)
   - To create and switch to a new branch from the terminal, run this command
  
      > git checkout -b "branch-name"

- You can add changes to your branch via a 'commit'
   - To add (aka stage) changes to your commit, run this command (you can replace [name of modified/created file or folder] with `.` to add all changes)

      > git add [name of modified/created file or folder]

   - To see what files and folders you have changed / created, and whether you staged them for commit, run this command

      > git status

   - To commit the staged changes, run this command

      > git commit -m "a short message that describes the changes in this commit"
   
- It is easy for small things to go wrong when committing changes

   - You may see odd files or folders you don't know the purpose of (such as various config files), so double check what should add should not be committed to the repo before staging something odd
  
   - The `-m` in `git commit -m` specifies that you are adding a message to this commit. Do not forget the `-m` or to actually type out your message, because a message is mandatory, and if these things are ommitted you will be forced to add a message anyway via Vim. If you get trapped in Vim, either just close the terminal and start over, or read the guide on how to Vim.
   
- Once you have committed your changes, they need to be added to the repository
   - Push your changes to the repository by running this command
  
      > git push

   - If this is your first push on this branch, the repository doesn't have a coressponding branch. To create a branch in the repository and push your commit, run this command. Afterwards, there should be a pop-up on the repository asking if you want to create a pull request.
  
      > git push --set-upstream origin [branch name]
 
   - If you want to add more changes to a pull request, you can mark the pull request as a draft on GitHub. Once you have made, staged, committed, and pushed all the changes you want to add to a pull request, remove the draft status so someone can review and approve it so the changes can be merged.

   - Once a pull request is merged, GitHub will ask you if you want to delete the repository branch, since its associated pull request is closed. You can delete the local branch by running this command

      > git branch -d [branch-name]

<br>

### Pulling Changes from Repository

1. Make sure you are on the main branch (the one branch not associated with any pull requests)
   - You can see all branches and your currently selected branch by running this command

      > git branch

   - If you are not on the main branch, you can switch to it by running this command

      > git checkout main

2. Pull down new changes from the repository by running this command
   > git pull

<br>

## Programming Things

### Navigating File Structures via the Terminal

- Running `cd [file path]` allows you to switch to whatever directory was specified in the file path (as `cd` stands for "change directory")
  - These file paths can be relative to the current directory, or absolute paths
- Running `ls` shows you all the items in the current directory
- `.` means current directory, and `..` means one directory up
- If you know what you are doing, you can use a file path to get exactly where you need to go
- If you are uncertain of the directories on your computer, you can use `cd [directory]` and `cd ..` to go up and down directory levels, then check where you are using `ls`, until you find where you need to be

<br>

### Using Vim
- To quit Vim and save any changes, type `:wq`, which stands for "write and quit"
- To quit Vim without saving changes, type `:q`
- To move your cursor, use the arrow keys (or page up and page down) 
- To edit text in Vim, press "I" on your keyboard to enter 'insert mode', which will allow you to edit text
- To exit 'insert mode', press esc

<br>

### Running Java Program From Terminal With Gradle
- Navigate to the uppermost directory of the project in the terminal and run `./gradlew build` to build the project
- This will generate a .jar file that contains class files (the compiled .java files) and a manifest that has instructions for what to do if the .jar file is run with Java (in stitch its in stitch/app/build/libs)
- To run the program, copy the .jar file and send it to the machine you want to run the program on
- Install Java on that machine (if it isn't installed already), then run `java -jar FileName.jar` to run the program

<br>

## GitHub Things

### Adding ssh Keys to Your Account

*Add ssh keys to allow you to clone repositories to your local device.*

1. Open the terminal and run this command

   > ssh-keygen -t ed25519 -C "your_email@example.com"

2. It will then prompt you to choose a save location. The default location is fine, so just hit enter.
3. It will then prompt you to type and retype a passphrase. This is in case someone gains access to your computer, they don't have access to your ssh keys. Having no passphrase is fine, so just hit enter.
4. Start the "ssh key agent" by running this command

   > eval "$(ssh-agent -s)"

5. Add your private ssh key to the key agent by running this command (note that if you choose a different name for your key, use that instead of "id_ed25519")

   > ssh-add ~/.ssh/id_ed25519

6. Then you can add the public key to your GitHub account
7. Do this by cat-ing the public key file with this command and copying the whole output
   > cat ~/.ssh/id_ed25519.pub
8. Then go to the ssk key section of the setting in your Github account, click the button to enter a new ssh key, then add the public key and name it based on your local device

<br>

### Making a Repository

*A repository is a place to store code. People can add, change, remove, and use code via repositories.*

1. Click the plus icon at the top right of GitHub page and make a new repository
2. Fill in information such as...

   - Its name (which can be changed later with some effort)

   - A description if you want

   - Whether it is public or private (can make it private until your project is in more organized state)

   - Whether to add a readme (which you probably do want to do)

   - If there is a .gitignore (you can choose from a bunch of templates GitHub has based on which language you are using)

   - And which lisence you will use (can change later)

4. Then click create and you will have a repository

<br>

### Cloning a Repository

*Cloning a repository allows you access the code on your local machine.*

1. Make sure you have an ssh keypair to allow your local machine to access your account (so the public key in your GitHub account and the private key on your machine)
2. Make sure you have git installed on your machine <br>
   for Linux, run this command in the terminal
   > sudo apt install git-all
   
   for MacOS, run any git command, such as the one below. If git is not installed, you will be prompted to install it

   > git --version
   
   For Windows, just switch to another operating system
   
4. Open the terminal and navigate to the directory where you want the project directory to be located
5. Run this command, where `[repository page]` is the URL like thing copied from the webpage of the repository (click the green "code" dropdown, go to the ssh section, and copy that string of text).
   > git clone [repository page]
6. You have successfully cloned a repository, and can now open your IDE and open the project directory from wherever you saved it to start working on your project.
