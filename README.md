# Intro to Git

*For those of you who like videos, follow this guide with me here!* https://www.youtube.com/watch?v=18gA0PB6mBw&t=369s 

Git is a popular version control system which allows for tracking file changes and is a great tool for source code management and collaboration. 

# Git vs GitHub? 
A common misconception i've heard peers have is that Git and GitHub are the same thing!
NOPE
Infact their functions are completely unique to one another!

**Git is** a tool used to manage versions of files and to transfer files in Git repositories. 

A *Git repository* is esentially where your a given project lives. The git repository will contain a .git folder inside of the project directory. 

**GitHub is** a cloud based server for uploading Git repositories. 


## ⚡️ Setting up Git 

# 1 Download Git: https://git-scm.com/downloads

If you would like to have a reference to use to set up Git, this is a great reference: https://adamtheautomator.com/git-bash/

For this tutorial I will be using Git Bash. We will have access to linux commands through the Git CLI (Command Line Interface).

Here are basic linux commands that are good to know:
https://www.guru99.com/linux-commands-cheat-sheet.html

The more you remember and learn to use em, the more power you have on the command line!

# 2 Have a GitHub account! 


## ️️Configure access to GitHub repositories
In the Git bash we will generate your SSH keys:

`ssh-keygen -t rsa -b 4096 -C "yourgithubemail@blank.edu"`

More on ssh-keygen here: https://man7.org/linux/man-pages/man1/ssh-keygen.1.html

This command will create an SSH key for you to use. When running this command you can accept the defaults for the fields. I do not recommend changing the filename where the key is stored from the default location!

When you get to ‘ enter a passphrase ‘ for your key. I suggest that for security purposes you do choose to have a passphrase but make sure it is memorable to you. You will be asked to use this whenever you try to access resources in your GitHub account using the git command line tool. 

To view the contents of this file that gets created we can use cat (this is a linux command) which is used to ‘concatenate’ aka read data from the given file and output it. Very useful if you don't want to open up your file in an editor to see its contents. 

After the ssh key is generated you can view it by using the command:

`cat ~/.ssh/id_rsa.pub`

Some more info on `cat` ! https://www.geeksforgeeks.org/cat-command-in-linux-with-examples/

Now that we’ve created our key - we are going to associate it with our Github Account.

If you go to https://github.com/settings/keys this is where your SSH keys live. We are going to give our Key descriptive name. In the Key section add the output on our Git Bash terminal from the cat command and press ‘Add SSH Key’

A successful addition looks like your SSH Keys showing up under authentication keys. 

If you are having any trouble go checkout: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent


Now we will go back to the Git Bash and configure our Github user on there. 
Lets first cd (change directory) into the directory we want to use

Then lets run the following commands:
`git config --global user.email yourgithubemail@blank.edu`
`git config --global user.name "Your Github Username"`
`git config –global user.password “your ssh key”`
`git config --global user.password "1234321"`
For the configuration of the password above, add in your ssh key.

To save your configuration!!!
Otherwise you’ll have to resign in every time you try to access Github using git. 
`git config --global credential.helper store`

To see your newly saved credentials, be aware that this will show your password as a string! 
`git config --list`

Okay so - if all has gone well you can now..

##Clone a repository
You can now go and clone my repository for this project!

Go to the following link: 
https://github.com/Alinamoo/IntroToGit

OR use

`git clone git@github.com:Alinamoo/IntroToGit.git “name your directory”`

cd into the newly cloned repository.

`git remote remove origin`
Now we’re going to give this repository a new origin.

First, go ahead to your GitHub page and lets create a new repository:

Copy the SSH link from the newly created repository like we did when cloning the first repository:
`git remote add origin git@github.com:yourusername/yourreponame.git`
`git push -u origin main`

If all has gone well in setting up your Github repository then you will get a successful message.

Now that we have our environment set up, we are ready to start development!

## Create!
So go ahead and create a file. Whatever you’d like - let’s take 5 mins to create a file. 

## Stage and Share

`git status`
You'll see all the files you've made edits to. The files in red are those that have edits and can be added your commit.

`git add “file”`

`git commit -m “add your commit message”`

`git push origin main` 

If all has gone well you will see your file/s upload! Refresh your GitHub and see your recent push. 

**Would you like to see a continuation of this Git Intro?**

It would include:
- Isolating work in branches
- Integrating changes
- Stashing Temporary commits
- Inspecting Branch changes  
- Reviewing code: Pull requests
- Best practices for developing code when collaborating

Hope you took away an some peice of knowledge, insight, or just even humor from this!

Alina Momin

