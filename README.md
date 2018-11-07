# QMIND-Kaggle-Titanic

Hey everyone! This is our main repository for our project. 

This readme contains instructions on how to get everything set up for Kaggle. Before following these instructions, please make a github account and tell me your username so that I can add you to this repository. You won't be able to do the things listed here if I don't add you to this repo.

Also, if you get stuck at any point, feel free to shoot me a slack message.

# Step 1. Install Stuff

## Installing Git

This section is split into windows and mac sections. If you're on windows, follow the windows section, and vice versa. If you have some of these things already installed, then feel free to skip the corresponding instructions but still make sure the test scripts work.

### For Windows:

1. Download git bash [here](https://git-scm.com/downloads)
2. Create a folder somewhere on your computer named QMIND.
3. Inside that folder, right click anywhere and choose "git bash here". It should open up a terminal.
4. In the terminal, enter the following, replacing USERNAME and EMAIL with your own github account info:   
`git config --global user.name USERNAME`  
`git config --global user.email EMAIL`
5. Enter the following to download this repository onto your computer:  
`git clone https://github.com/johngao2/QMIND-Kaggle-Titanic.git`  
After you do this, you should have a new folder in QMIND named QMIND-Kaggle-Titanic. This folder is your local version of our titanic repository.
6. Enter the new folder by typing `cd QMIND-Kaggle-Titanic`
7. You'll be able to confirm that you're in the QMIND/QMIND-Kaggle-Titanic folder by looking at the terminal prompt. If it doesn't say QMIND-Kaggle-Titanic, then you're in the wrong folder.
8. We'll be ignoring software best practices for now and use only two branches. Right now, if you type `git status`, it should tell you that you're in the master branch.
9. Switch to the development branch by typing `git checkout development`
10. Do another `git status` to make sure you're not in the master branch.
11. Create a folder by typing `mkdir YOURNAME`. This is where you'll put your stuff. The general rule is to never edit or delete stuff from other peoples' folders, but it's OK to copy stuff over to your own folder.

### For Mac:

1. Create a folder somewhere on your computer named QMIND.
2. Open up terminal, and type in:  
`git config --global user.name USERNAME`  
`git config --global user.email EMAIL`  
2. Navigate to your QMIND folder using the `cd FOLDERNAME` command. To see what folders are in your current directory, you can enter `ls`. For example, my terminal starts in the folder named 'johngao'. If I want to get to johngao/work/QMIND, then I just have to type `cd johngao/work/QMIND`.
3. Once you're in your QMIND folder, type:  
`git clone https://github.com/johngao2/QMIND-Kaggle-Titanic.git`  
4. Follow steps 6-11 on the Windows instructions.


## Installing anaconda

This is more or less the same for mac and windows. Note that even if you already have python 3.xx, I still recommend getting anaconda just so that we're all using the same python distribution. 

1. Go here https://anaconda.org/anaconda/python/files?version=3.6.5 and download the appropriate version
2. Follow the onscreen instructions. There may be an option to add anaconda to your PATH variable; I recommend checking this even if anaconda doesn't recommend it. It makes things easier.
3. In terminal (if mac) or the newly installed anaconda prompt (if windows), type in `conda list`. It should come up with a list of installed packages. If it doesn't, you did something wrong.
4. Now type in `jupyter notebook`. It should open up a new chrome tab with the jupyter logo on it. Try creating a new python notebook and run `print('Hello World')` or something. If this works, you're set!

**IMPORTANT NOTE**

If you have Anaconda, **DON'T USE PIP INSTALL TO INSTALL PACKAGES**. First google it to see if there's a `conda install PACKAGENAME` available. If there is no conda install option, then you can use pip install.

# STEP 2. Python Basics

Make a datacamp account if you haven't yet, and do the following datacamp lessons:
https://www.datacamp.com/courses/intro-to-python-for-data-science  
https://www.datacamp.com/courses/intermediate-python-for-data-science

If you don't know python, they'll probably take 3-4 hours each. If you do know python, they'll take a lot less time, but you should still do them just to review and fill possible knowledge gaps. For example, I did these two when I knew python and they only took like 50 minutes each so it's not a huge commitment.

That's it for this week! See you at next week's meeting!
