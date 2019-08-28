# Intro to Github

Hi! I am [Anna](https://twitter.com/IkokiAnna).

Here is a quick intro to Github, some other random explanation, simple try outs, links to more info, and how to *git* started.

## Table of Contents

1. Basic Concepts

 * Git
 
 * Github

2. Download Git

3. Version Control System (VCS)

4. Git Operations 

  * Create New User Account or Sign In
  * Create (New) Repository
     * In github
     * Using Command Line
  * Make some changes (update file)
  * After making some changes
  * Merging the changes
  * Merge Conflicts
  * Project Release

5. Other VCS

==================================================


## 1. Git - Basic Concepts

[Git](https://git-scm.com): **Software** for source code control (cloud).


GITHUB: **Online service (website)** which hosts Git. It is a popular open source social network for coding community. 


## 2. Installation of Git

To have version control for the code using github, you need to [download git](https://git-scm.com), as github is a **web interface** built around a VCS (git).

It is open source, and FREE.

## 3. [Version Control System (VCS)](https://en.wikipedia.org/wiki/Version_control)

Tracks and control change during development and maintainenace of code (electronic documents). It allows software developers to work together and sometimes simultaneouely without overwriting each other's changes while maintaining the history of every version.

## 4. Git Operations

### [Create an account on Github](https://github.com) or [sign in to Github](https://github.com/login)
***

### <a name="repo">How to create (new) repositories </a> 
***

##### In github website

* At your dashboard: Click **New** button.
Name your repository (file/folder). 

* By forking: Click **Fork** button from existing repository.

* By cloning: Copy the HTTPS web url and paste it into the command line Terminal.

* By downloading: Click the **Download** button to Open in Desktop or Download Zip.


#### Using Command Line

* With an existing file in your computer desktop.

		cd ~/Desktop/directoryName
		git init	
		git checkout -b develop	
		touch fileName.md  //make an empty file
		
This will create a new git repo to manage the current folder.	

Edit this fileName by adding or removing a line(s) and save it. 

But we want to save this remote. If you had created the project in github, copy its HTTPS / SSH clone url which looks like `git@github.com:UserName/repoName.git` or `https://github.com/UserName/repoName.git`

Then add the remote

		git remote add origin <url>
	
Finally, push the existing repo
 
		git push -u origin master
		
 * By creating a new file

		echo "# repoName" >> fileName
		git init
		git add fileName //commit
		git remote add origin <github repo url>
		git push -u origin master
		
	>Origin is remote-server name, while master is just a branch-name. Master is a default branch name of the repo.

* By cloning an existing repo on your desktop.

Clone mirrors whole repository. The remote repo will be downloaded and copied in your local repo. You can perform operations using this local repository. You do not need network to do this, until during synchronization.
  
		cd ~/Desktop
		git clone <git-repo-url> directoryName
		cd directoryName
		git checkout -b develop //to update the dev 
		git checkout -b myFeatureBranch //create branch
	
It will also add a remote named 'origin' back to source

This will create a folder named directoryName and clones the repo there and adds a remote named "origin" back to the source. 'remote' is automatically created when cloning.

If you leave the name part out, it will clone to the folder with the repo original name


>Do NOT commit directly to master-branch NOR develop-branch directly to the repository.
>
>Instead, CREATE ***feature-branches*** for unit issues


### <a name="change"> Make some changes (update files) </a> 
***
	git checkout develop
	git checkout -b myFeatureBranch
		
### <a name="change"> After making some changes </a> 
***		
	git add .  //commit this revision changes 
	git commit -m <message explaining changes> //saving/adds
	
### <a name="change"> Merging the changes </a> 
***	 
	git checkout develop
	git merge -- myFeatureBranch
	git push origin develop //stores changes to Git repo
	
This will add those features/edits to the develop branch.
	
### <a name="change"> Merge Conflicts </a> 
***	
     git pull
   
**Pull** copies changes from remote repo to local one.

### <a name="change"> Project Release </a> 
***
	git checkout master  //feature branch created 
	git merge -- develop  //update to develop branch
	git push origin master  
	git tag v1.0   //tag is name with a release version
	git push origin v1.0.0
	
This will add the develop branch total features to the master in the final release. 

**Push** copies changes from local to remote repo to store permanently in Git repo.
It is used for synchronization between two repos.

NOTE: After merging with master branch you can delete develop branch

>Most of these operations (commit, branches creation, etc can be performed offline. Internet is required only when  publishing changes (push) or taking latest changes (pull).

### <a name="change"> Deleting a Repo </a> 
***

In the repo dashboard, click **setting**, scroll to the bottom, and delete. Make sure of this before doing so, as you can't recover the deleted repo.

## 5. Other VCS

+ [Github](https://github.com)
+ [Gitlab](https://about.gitlab.com) 
+ [Tortoise svn](https://tortoisesvn.net) 
+ [Bitbucket](https://bitbucket.org)
+ [Dropbox](https://www.dropbox.com)
+ [Google Drive](https://www.google.com/drive/)
+ [Sharepoint](sharepoint.com) (microsoft)
+ [Time Machine](https://en.wikipedia.org/wiki/Time_Machine_(macOS))(macOS)
+ Wikis: [Wiki.js](https://wiki.js.org), [Tikiwiki](https://tiki.org/tiki-index.php), [Nuclino](https://www.nuclino.com), [Mediawiki](https://www.mediawiki.org/wiki/Manual:What_is_MediaWiki%3F)
+ Other Code Sharing Sites for building, collaboration, hosting and sharing: [repl.it](https://repl.it), [plunker](https://plnkr.co)	

### Did I miss anything? 

Drop me a line on [twitter](https://twitter.com/IkokiAnna)

Also feel free to fork this repo and change it to your liking.