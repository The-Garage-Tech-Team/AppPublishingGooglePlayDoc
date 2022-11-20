# App Publishing Google Play


![Image of Garage](https://pbs.twimg.com/profile_banners/1473251190611877889/1643650277/1500x500)


# The Complete Guide for Publishing your App in Play Store

## Table Of Content 
- [Pre-Publishing](#PrePublish)
  * [Change Package Name](#packageName)
  * [Privacy Policy](#Policy)
- [Release & Publishing](#publish)
  * [Git Init](#Git-Init)
  * [Common Errors](#errors)
- [Resources](#Resources)
  * [Documentation](#docs)
  * [Video Links](#videos)



<a name="PrePublish"/>
<a name="packageName"/>
<a name="publish"/>
<a name="errors"/>
<a name="docs"/>
<a name="videos"/>
<a name="Policy"/>
<a name="Resources"/>
<a name="Git-Push"/>
<a name="Git-Pull"/>





## Pre-Publishing



## Change Package Name
You need to use a different **package name** because "com.example" is restricted

1. You need to set the package name using the applicationId in your project's build.gradle file:

```
defaultConfig {
        applicationId "com.example.yourProject"
  
    }
```
Change it into something unique for example:
```
defaultConfig {
        applicationId "com.developerName.yourProject"
  
    }
```
2. Then you can right-click on the package in your main/java folder and select Refactor > Rename. Select Refactor Package and type the new one you just used in applicationId.

3. You'll need to re-sync Gradle and rebuild the project after this, of course. :)


## Privacy Policy


GitHub is a web-based interface that uses Git that lets multiple people make separate changes to web pages at the same time.
<img width="1593" alt="GitHub" src="https://user-images.githubusercontent.com/71218097/196057839-d9999dfa-8a84-47fb-b563-104766f073ef.png">
	
## What is repository?
To be very clear, a Git repository is the directory where all of your project files and the related metadata resides.
### types of repositories:
1. Central repository
2. Local repository 

<img width="916" alt="Central Repository" src="https://user-images.githubusercontent.com/71218097/196057855-772e6903-fd1e-4984-8a3f-74f8e64eefba.png">

Git records the current state of the project by creating a tree graph from the index. It is usually in the form of a Directed Acyclic Graph (DAG).

## Features of Git
1. Distributed
*  Allows distributed development of code 
* Every developer has local of copy the entire development history and changes are copied from one repository to another
2. Compatible
* Compatible with existing  systems protocols
3. Non-linear
* Supports non-linear development of software
4. Branching
* It takes only few seconds to create and merge branch
* Master or main branch always contains production quality code 
5. Lightweight
* Uses lossless compression technique to compress data on the client’s side
6. Speed
7. Open source
8. Reliable
* On events of system crash the lost data be easily recovered from Amy local repositories of the collaborators
9. Secure
10. Economical
* Releases under GPL’s license it is for free

## Operations & Commands
Some of the basic operations in Git are:
1. Initialize
2. Add
3. Commit
4. Pull
5. Push
Some advanced Git operations are:
1. Branching
2. Merging
3. Rebasing

<img width="725" alt="repositories" src="https://user-images.githubusercontent.com/71218097/196057879-0e5d0412-d857-436b-922d-cb0067caca3f.png">

Let me first give you a brief idea about how these operations work with the Git repositories. Take a look at the architecture of Git below:

<img width="516" alt="working" src="https://user-images.githubusercontent.com/71218097/196103021-c18f3b96-7b7b-4c1b-bb53-b6b5c81a15ce.png">


If you understand the above diagram well and good, but if you don’t, you need not worry, I will be explaining these operations in this Git Tutorial one by one. Let us begin with the basic operations.


## Release & Publishing

![Git Command Flow](https://miro.medium.com/max/1400/1*69prApOy8_cZPnmRHGHQZg.png  "Git Command Flow")

Git is an important part of daily programming and is commonly used in the software industry. Here are listed commands that are commenly used that every developer should know.



### Git Init
The `git init` command creates a new Git repository. Executing `git init` creates a `.git` subdirectory in the current working directory, which contains all of the necessary Git metadata for the new repository.

### Common Errors

The `git status`command  lets you see which changes have been staged, which haven’t, and which files aren’t being tracked by Git. Status output does not show you any information regarding the committed project history. For this, you need to use `git log`.

We can gather information like:

- Whether the current branch is up to date
- Whether there is anything to commit, push or pull
- Whether there are files staged, unstaged or untracked
- Whether there are files created, modified or deleted

### Git Add
Adding changes from "Working Directory" to Git's "Staging Area".

- To Add a single file:
```
git add <file name>
```

- To add everything in once :
```
git add .
```

**Important: The git add command doesn't change the repository and the changes are not saved until we use git commit.**

### Git Commit
Taking snapshots to your work and moving it from the "Staging Area" to Git's "Repository"
When Commiting, you need to write a message to explain what you did or developed

```
git commit -m "commit message"
```


### Git Branch 
Branches are highly important in the git world. By using branches, several developers are able to work in parallel on the same project simultaneously.
We explained **here** in details about `git branch` including how to create, delete, and merging them.

### Git Push

After committing your changes, the next thing you want to do is send your changes to the remote server. Git push uploads your commits to the remote repository.

```
git push <remote> <branch-name>
```

**However**, if your branch is newly created, then you also need to upload the branch with the following command:

```
git push -u origin <branch_name>
```

**Important: Git push only uploads changes that are committed.**

### Git Pull
`git pull`is  a command used to update the local version of a repository from a remote. It does two thing:
does two things.
- Updates the current local working branch (currently checked out branch)
- Updates the remote tracking branches for all other branches.

``` 
# General format
git pull

# Pull from specific branch
git pull REMOTE-NAME BRANCH-NAME
```

### Git Clone
The `git clone` command is used to create a copy of a specific repository or branch within a repository.
```
git clone <Repository URL>  

```

## Resources


## Documentation

One feature that is provided by git is the ability to create branches in your repository be it local or remote. Branches are named pointers that point to the last commit and can also show you commits prior to it. After your very first commit, a default branch, usually named “main”, will be created.

If a new branch is created after commits were made in a default branch, this new commit will contain the commits of this default branch in its history and the head will point to it as long as it’s the branch that’s currently active.



![](https://wac-cdn.atlassian.com/dam/jcr:a905ddfd-973a-452a-a4ae-f1dd65430027/01%20Git%20branch.svg?cdnVersion=582)


## Video Links


#### [Change Package Name](https://www.youtube.com/watch?v=qo-iCbPAi5k&ab_channel=CodeProf)


#### [Publishing the Android Version of the Flutter App to the Play Store](https://www.youtube.com/watch?v=mUpF8R6Nfcw&ab_channel=RomanJustCodes)



Typing  `git branch`  will show you all the branches created in this repository. If you see a branch name with an asterisk next to it (*) it means that  it’s the current active branch and is the one the head is currently pointing to.

You can also use this command to create and delete branches. For creating new branches you just need to add the new branch’s name .

```
 git branch 'new-branch-name'
```
If there is a branch that you want to delete, you just to need to add “-d” before the name of the branch that you want to delete.
```
 git branch -d   'branch-name'
```

One thing to keep in mind when adding a new branch is that you will still be on your default or currently active branch, and so you will need to manually switch to the new one before doing any new commits that you might want to do. 

You do this by typing checkout, followed by the name of your branch.
```
 git branch checkout 'branch-name'
```

One thing to note is that checkout is a very versatile command that can be used for different purposes other than switching branches. If you are in need of a command specifically for switching branches, you can you switch

```
 git branch switch 'branch-name'
```
## Merging branches

When you use the command  `git log`  to view your commits after you create a new  branch, it will show you the commits made in the default branch prior to it, with the head pointing to the very last commit. If you make a new commit in that new branch, the pointer will move to it, meaning that it’s now ahead of the default branch by 1, and it is a commit that the default branch does not have.

Say you want to bring the default branch to point to this new commit, you can accomplish this by merging. There are two common ways to do this:

* Fast Forward
* Three-way

Fast-forward is the more straight-forward one of the two,and it simply involves moving the history of one branch to the other to basically bring it up to speed with the target branch. This occurs if the current branch has not strayed too far from the target branch and made its own separate commits.



![](https://wac-cdn.atlassian.com/dam/jcr:d90f2536-7951-4e5e-ab79-f45a502fb4c8/03-04%20Fast%20forward%20merge.svg?cdnVersion=582)



However, if you have made commits in the current branch that have caused it to stray away form the target branch, this will cause three-way merging, where instead of moving one history to the other, it will combine the last two commits of each of the two branches  and connects them to a third one.


![](https://wac-cdn.atlassian.com/dam/jcr:91aece4a-8fa0-4fc3-bae9-69d51932f104/05-06%20Fast%20forward%20merge.svg?cdnVersion=582)


To do a merge, you simply switch to the branch that's behind, and then type `git merge`  followed by the name of the target branch.

```
 git merge 'branch-name'
```

## Conflicts

Conflicts are a very common occurence in merging branches. They mainly happen when a file is shared between two branches, and both of them have commits that contain different edits to the same file.
When Git detects such an occurence. It stops merging and lets you know that conflict has occured, leaving it up to you to solve it.You can then view these conflicts by opening the file that caused them.

When you open the file, it will contain symbols added by Git that indicate which parts caused the conflict. `<<<<` tell you the source branch of the edit , while `====` will indicate the part the was edited. From there, you as the merger will have to decide which part to keep to solve this conflict.
```
<<<<<<< main
this text was added in branch main
=======
this text was added in branch secondary_branch
>>>>>>> secondary_branch;
```

After solving the conflicts, you will then be free to add it and commit it like any normal file.


# GitHub Documentaion :

### What is the GitHub ?
##### GitHub is an online software development platform used for storing, tracking, and collaborating on software projects. It enables developers to upload their own code files and to collaborate with fellow developers on open-source projects.

### What is the repostorty ?
##### A repository contains all of your project's files and each file's revision history. You can discuss and manage your project's work within the repository.
### Building repositories from GitHub
######  1. On the left side click on new button to create (new repostorty)
  ![new repostorty](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/new%20repo.png?alt=media&token=9938ca76-a220-432b-87c5-320db7366f47 "new repostorty")
  
###### 2.  Enter the name of repostorty
  ![repostorty name](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/repo%20name.png?alt=media&token=a2d0b019-133c-4f20-9c76-306d9724c6ac "repostorty name")

### Building files in github
###### Click on creating a new file
![new file ](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/create%20new%20file.png?alt=media&token=87e1c1a4-c21f-4814-8101-72c56d151a00 "new file")
###### Enter the name of the file 
  ![file name](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/name%20of%20file.png?alt=media&token=801271e3-1267-4a76-9e66-523f9287477a "file name")
###### Write anything you want after that enter the name of commit  Write anything you want after that enter the name of commit 
![commit name](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/commit%20name.png?alt=media&token=9d59aca7-41b6-44ae-a70d-db17ce3c827c "commit name")
###### After enter the commit new file button the repostorty look like the picture below
 ![repostorty preview ](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/repo%20prev.png?alt=media&token=d3067611-c6e4-4da5-80c9-7c91edb7b880 "repostorty preview")
 
###### if you want to edit file click on the edit button on the right side
![edit file](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/edit%20file.png?alt=media&token=1df1dae4-c2ea-44ba-8a62-a378a330b502 "edit file")
### Building branches in github
  ![branch]( https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/branch.png?alt=media&token=2fcc3ee3-2153-441d-86f3-df92bd67e7f0 "branch")
###### On the right side click on the new branch button to create new branch   

  ![new branch](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/new%20branch.png?alt=media&token=5f607e0f-151e-4578-b0f2-85a8ebfdfa0e "new branch")
###### Enter the branch name
![branch name](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/Screen%20Shot%201444-03-21%20at%209.20.27%20AM.png?alt=media&token=e61b04ba-ee28-4efd-aec9-f73f4625073b "branch name")

###### All branch's and active branch
 ![all branch and active.](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/Screen%20Shot%201444-03-21%20at%209.58.40%20AM.png?alt=media&token=0de910b6-2d40-41eb-b77f-87f49f71c003 "all branch and active.")
### Collaborating  
##### You’re a team player, so you’re going to need to add your team to your repo so they can collaborate. Once your team is added as collaborators they’ll be able to push, merge, and a ton of other destructive things so make sure you’re only adding your teammates.

![setting](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/Screen%20Shot%201444-03-21%20at%2010.06.39%20AM.png?alt=media&token=f3298516-8d19-48f5-8cf3-9dc580e7f770 "setting")
###### Click on the “Settings” tab of your repo, then “Collaborators” 
![collaborators](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/Screen%20Shot%201444-03-20%20at%201.52.31%20PM.png?alt=media&token=5b5fb012-4ce5-4b5d-b4ed-5031703296da "collaborators")
###### Click on add people button to search for Github users
![add people](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/Screen%20Shot%201444-03-20%20at%201.52.37%20PM.png?alt=media&token=226e5505-aa10-4a11-9190-6dc077c320af "add people")
###### Add them by clicking “Add Collaborator”
![add a collaborator](https://firebasestorage.googleapis.com/v0/b/todolist-a8a37.appspot.com/o/Screen%20Shot%201444-03-20%20at%201.52.44%20PM.png?alt=media&token=da96c29e-10c0-4ae0-a327-0fcd12bce049 "add a collaborator")


https://www.termsfeed.com/blog/sample-mobile-app-privacy-policy-template/
