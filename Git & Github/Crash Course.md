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
this command takes us back to the Desktop

Go to Github > git-journey > Code > Local > HTTPS
* copy this link and paste it into the terminal using git clone
```bash
git clone https://github.com/harryra-git/git-journey.git
```
