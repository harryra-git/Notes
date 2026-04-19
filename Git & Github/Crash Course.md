# Git & GitHub Crash Course (For Beginners)

## Git vs GitHub

**Git:** is the Coffee
 * runs locally on your computer
 * tracks changes you make to your files
 * keeps everything organized

**Github:** is the Coffee Shop
 * Merges multiple versions of the document/gits together
 * Online server where the entire project lives

Essentially, it is a version control system for photos, videos, codes, or documentation

## Git Architecture (Local vs Remote)

### Local
refers to your own computer; this is where your files, code, and every change you make are stored.

**Local Gits Workflow:**
 * **1. Working Directory:** the folder where your project is located
   * write code
   * create new files
   * modify existing files
 * **2. Stage:** next step once the changes are ready from the working directory
 * **3. Local Repository:** temporary area where files site between working directory and repository save

**Commit**: permanently saving the changes made to the local repository locking it in as a recorded version of the project history.

**Repository:** a place where all the versions of your files and their complete change history are stored; think of it as a digital cabinet for your code.
 * Git - Local Folder
 * GitHub - Cloud Server

### Remote
Lives in the cloud; where you push or upload your local work
 * share codes with others
 * access it from another computer
 * keep it safely backed up

**Push:** moving from Local Repository to remote repository; uploading the repository to github

## Getting Started: Installation and Setup

### Installation
 * **Windows**: Download the installer from the official Git website. It typically includes **Git Bash**, a terminal preferred by many developers
 * **macOS**: Install via the official site or using **Homebrew**.
 * **Linux**: Follow the distribution-specific guide on the Git website.

**Verification**

To check if Git is installed, run:
```bash
git --version
```

### Creating Git Repositories

**Terminal Commands:**

1. **```cd:```** **(Change Directory)**:

   command in terminal to **change directory**; moving from one folder to another
   ```bash
   cd Desktop
   ```
2. **```pwd```** **(Print Working Directory)**

   displays the full path of the directory (folder) you are currently in
   ```bash
   pwd
   ```
3. **```touch```**

   creates a file with the name and extension you specify. If the file already exists, it simply updates the "last modified" timestamp without changing the content
   ```bash
   touch filename.txt
   ```
   **Tip:** you can create multiple files at once: ```touch index.html styles.css script.js```

4. **```mkdir```** **(Make Directory)**
   creates a new directory (folder) in your current location
   ```bash
   mkdir NewFolderName
   ```
   **Tip:** If you want to create a folder inside another folder that doesn't exist yet, use the ```-p``` flag: ```mkdir -p photos/2026/vacation```. This builds the entire "path" in one go.
5. **```open```**
   
   **Tip:** "." means current folder; ".." means go back one folder ```cd ..``` (goes back one folder) or ```open .``` (opens the current folder)
6. **```init```** **(Initialize)**

7. **```ls```** **(List)**
   
   lists down the contents of the current folder/directory
   * to view hidden files and folders in the folder/system:
      ```bash
      ls -la
      ```

**Creating files on Desktop/Local**
1. Change Directory to Desktop
   ```bash
   cd Desktop
   ```
2. Create a Folder called "git-one" on Desktop
   ```bash
   mkdir git-one
   ```
3. Change directory to the "git-one" folder
   ```bash
   cd git-one
   ```
4. Create two text files in "git-one" folder
   ```bash
   touch one.txt
   touch two.txt
   ```
5. Create a folder within "git-one"
   ```bash
   mkdir myFolder
   ```
6. Create a text file within "myFolder"
   ```bash
   touch three.txt
   ```
   ### Initializing Git on Desktop
   1. Go back one folder
      ```bash
      cd ..
      ```
   2. Open git-one folder
      ```bash
      open .
      ```
   3. Initialize git folder
        ```bash
       git init
        ```
   4. Verify git initiation
       ```
       ls -la
       ``` 
       this should list down the filder contents with a **".git"** extension.

**Creating files on GitHub**
1. Go to GitHub Website
2. Create a repository (git-journey)
3. create two files
   * one.txt - enter 'one' and **commit** changes
   * two.txt - enter 'two' and **commit** changes

## Cloning a Repository (git clone)
*Assume that the current directory in the terminal is git-one*
```bash
cd ../
```
this command takes us back to the Desktop/Root Folder

1. Go to Github > git-journey > Code > Local > HTTPS
   * copy this link and paste it into the terminal using git clone
   ```bash
   git clone https://github.com/harryra-git/git-journey.git
   ```
2. Check the cloned repository from GitHub
   ```bash
   ls
   ```
   this should list down two folders: 1. git-journey (from GitHub) and 2. git-one (Local Git)
3. Go to git-journey and check for ".git" files to verify clone
   ```bash
   cd git-journey
   ls -a
   ```
   this should provide the contents from the folder including .git together with the two text files created from GitHub (one.txt and two.txt)

## Tracking Changes (git status)
1. Open git-journey and edit one.txt (add "1")
   ```
   one
   1 
   ```
   Do the same thing with two.txt (add "2")
   ```
   two
   2
   ```
2. In the terminal, run git status to check for modified files
   ```bash
   git status
   On branch main
   Your branch is up to date with 'origin/main'.
   
   Changes not staged for commit:
     (use "git add <file>..." to update what will be committed)
     (use "git restore <file>..." to discard changes in working directory)
	   modified:   one.txt
     modified:   two.txt
   
   no changes added to commit (use "git add" and/or "git commit -a")
   ```
   this highlights that **one.txt** has been modified

## Staging Changes (git add and git reset)
Phase where you can review, adjust, and remove changes before permanently applying to the main branch

**Adding:** The process of moving changes from the working directory to the staging area

**Move everything to the staging area**
```bash
git add --all
git add -A
```

**Stage the changes only within the current directory**
```bash
git add .
```
*note:* simplest way to stage all changes is to navigate to root directory and run ```git add .```

**Stage new or modified files (not deleted ones)**

Stages all visible changes except for deleted files
```bash
git add *
```

**Stage files by extension**
```bash
git add *[file extension]
git add *.txt //sample
```
*Note:* stages changes it finds in the root folder. it won't include deleted files or files inside subfolders.

**Stage specific file**
```bash
git add [fileName].txt //specific file
git add [folderName]/[filename].txt //file under a folder
```

**Remove from the staging area and return to working directory**
```bash
## This does not bring back deleted files; only resets from staging area
git reset

## to restore everything even deleted files
git reset --hard
```

**Sample (git add -all and git reset) using git-journey**
```bash
harryra@Harrys-Mac-mini git-journey % git add --all
harryra@Harrys-Mac-mini git-journey % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   myFolder/three.txt
	modified:   one.txt
	modified:   two.txt

harryra@Harrys-Mac-mini git-journey % git reset
Unstaged changes after reset:
M	one.txt
M	two.txt
harryra@Harrys-Mac-mini git-journey % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   one.txt
	modified:   two.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	myFolder/

no changes added to commit (use "git add" and/or "git commit -a")
```

**Sample (git add -A and git reset) using git-journey**
```bash
harryra@Harrys-Mac-mini git-journey % git add -A
harryra@Harrys-Mac-mini git-journey % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   myFolder/three.txt
	modified:   one.txt
	modified:   two.txt

harryra@Harrys-Mac-mini git-journey % git reset
Unstaged changes after reset:
M	one.txt
M	two.txt
harryra@Harrys-Mac-mini git-journey % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   one.txt
	modified:   two.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	myFolder/

no changes added to commit (use "git add" and/or "git commit -a")
```

**Sample (git add . and git reset) using git-journey**
```bash
harryra@Harrys-Mac-mini git-journey % git add .
harryra@Harrys-Mac-mini git-journey % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   myFolder/three.txt
	modified:   one.txt
	modified:   two.txt

harryra@Harrys-Mac-mini git-journey % git reset
Unstaged changes after reset:
M	one.txt
M	two.txt
harryra@Harrys-Mac-mini git-journey % cd myFolder
harryra@Harrys-Mac-mini myFolder % git add .
harryra@Harrys-Mac-mini myFolder % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   three.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   ../one.txt
	modified:   ../two.txt

harryra@Harrys-Mac-mini myFolder % git reset
Unstaged changes after reset:
M	one.txt
M	two.txt
```

**Sample (git add . and git reset) using git-journey**

*delete two.txt and create four.txt with the value "four"*
```bash
harryra@Harrys-Mac-mini git-journey % git add --all
harryra@Harrys-Mac-mini git-journey % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   myFolder/three.txt
	modified:   one.txt
	modified:   two.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	deleted:    two.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.DS_Store
	four.txt

harryra@Harrys-Mac-mini git-journey % git add *
harryra@Harrys-Mac-mini git-journey % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   four.txt
	new file:   myFolder/three.txt
	modified:   one.txt
	modified:   two.txt

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	deleted:    two.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.DS_Store
```

## Saving Changes Permanently (git commit)

**Commit:** confirming and saving changes permanently

```bash
git commit -m "I have made some changes to the files"
[main 19c8c14] I have made some changes to the files
 Committer: Harry Aquino <harryra@Harrys-Mac-mini.local>
 5 files changed, 3 insertions(+), 1 deletion(-)
 create mode 100644 .DS_Store
 create mode 100644 four.txt
 create mode 100644 myFolder/three.txt
 delete mode 100644 two.txt

git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

### Add Git Identification
In order for git to track who made the changes
```bash
## Your email
git config --global user.email "you@example.com"
## Your name
git config --global user.name "Your Name"

##To save to a particular repository
git config --local user.email "you@example.com"
```

## To rollback changes to working directory (git reset)
```bash
git reset HEAD~
Unstaged changes after reset:
M	one.txt
D	two.txt
harryra@Harrys-Mac-mini git-journey % git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   one.txt
	deleted:    two.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.DS_Store
	four.txt
	myFolder/

no changes added to commit (use "git add" and/or "git commit -a")
```
## Automatically delete a file and stage changes (git rm)
```bash
git rm [filename.extension]

## to delete a modified files which has not been committed yet
git rm -f [filename.extension] ##f = force
git rm -f four.txt ##sample

## removes a modified file in the staging area but keeps it in working directory
git rm --cached [filename.extension]

##sample - changed four.txt contents to say "Hello" instead of "four"
git rm --cached four.txt

## recursive - removes the folder and other subfolders or files recursively
git rm -r <Folder>

## if "-r" is not included, then only the mentioned folder will be removed
git rm <Folder>
```

## Reviewing Commit History (git log)
```bash
## long random strings are commit IDs
git log
commit bd45d32f02f458413fa47b01832848d64c514f2b (HEAD -> main)
Author: Harry Aquino <harryra@Harrys-Mac-mini.local>
Date:   Sun Apr 19 22:19:35 2026 +0800

    I have made some changes to the files

commit 41d0f8d055d7ecbfc2c89fd138e349242780f105 (origin/main, origin/HEAD)
Author: Harry Aquino <aquinoharryr@gmail.com>
Date:   Sat Apr 18 10:59:26 2026 +0800

    Add two.txt with initial content 'two'

commit f1af3f045f08a35a9d67c8e623df2156fee5294f
Author: Harry Aquino <aquinoharryr@gmail.com>
Date:   Sat Apr 18 10:58:52 2026 +0800

    Add one.txt with initial content 'one'

git log --oneline ##cleaner view of commit summary
bd45d32 (HEAD -> main) I have made some changes to the files
41d0f8d (origin/main, origin/HEAD) Add two.txt with initial content 'two'
f1af3f0 Add one.txt with initial content 'one'
```

## Git Branching Explained
**Branch:** separate line of development where you can work independently
 * **main:** default branch; called "master" before; this is where all work begins; project's central line of development

*note:* a new branch inherits the current state of the branch you are in

Branching allows users to have a **secure** and **organized** area to
 * **review**
 * **test**
 * and **manage**
 
 changes before merging to the main codebase

**Merge:** combining the changes from two branches into one

Examples or branches are:
 * staging
 * development
 * frontend
 * backend

### To see how many branches you have (git branch)
```bash
git branch
* main
```

### To create a new branch
```bash
git branch [branchName]
git branch development ## sample
git branch
  development
* main ## * shows in what branch you currently are
```

### To move to a different branch
```bash
git checkout [branchName]
git checkout development ## sample
Switched to branch 'development'
```

### To move to a specific version
```bash
git log --oneline
## copy the commitID of the version you with to go back to
git checkout [commitID]
## to go back to the original version
git checkout main
```

## Merging Branches (git merge)
```bash
git merge [branchName] -m "[Insert message here]"
## sample
git checkout main ## goes to main branch
## edit four.txt to add "4" as a new line
git add . ## move to staging
git commit -m "I changed four.txt and added additional 4" ## commit to main
1 file changed, 2 insertions(+), 1 deletion(-)
## move to development branch
git checkout development
## merge main contents with development branch
git merge main -m "Merging main into development"
Merge made by the 'ort' strategy.
 four.txt | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
## move back to main branch
git checkout main
## merge development branch with main
git merge development -m "Merging on main with development"
Updating 3fb5b22..7f2aa5d
Fast-forward (no commit created; -m option ignored)
 three.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 three.txt
## the updated four.txt and newly created three.txt should appear in the git-journey folder
```

**Merge Conflict:** same part of the same file has been changed differently in two branches
 * decide which version to keep or;
 * merging both versions yourself


(e.g
 * main branch: one.txt ```var topic = "React"```
 * development branch: one.txt ```var topic = "Javascript"```
 
 )

## Comparing Commits with one another (git diff)
To know which commands are added or deleted (newer commitID first before older commitID)
```
git log --oneline
ccb04af (HEAD -> main) update one.txt file
80200f5 (staging, development) Merge conflict solve
74b5423 changed 444 on four.txt
3ab0fc4 changed 44
7f2aa5d Merging main into development
3fb5b22 I changed four.txt and added additional 4
df568c2 I created three.txt and entered three there
bd45d32 I have made some changes to the files
41d0f8d (origin/main, origin/HEAD) Add two.txt with initial content 'two'
f1af3f0 Add one.txt with initial content 'one'
harryra@Harrys-Mac-mini git-journey % git diff ccb04af 80200f5
diff --git a/one.txt b/one.txt
index e0e45e2..19e5830 100644
--- a/one.txt
+++ b/one.txt
@@ -1,2 +1,2 @@
 one
-Hello
\ No newline at end of file
+1
\ No newline at end of file
harryra@Harrys-Mac-mini git-journey % 
```
**Push:** ```git push``` - sending changes to the remote repository (GitHub)

**Fetch:** ```git fetch``` - any changes in the remote repository you want to bring to local repository (remote changes are downloaded into your local repositories memory **but wont appear in the working directory yet**)

**Pull:** ```git pull``` - to bring the remote changes to the working directory
 * PULL = FETCH + MERGE

 ```bash
 ## Pushing to GitHub
 ## main
 git checkout main
 git push origin main
 ## enter email and classic token when prompted
 ## staging
 git checkout staging
 git push origin staging
 ## development
 git checkout development
 git push origin development
 ```

 
