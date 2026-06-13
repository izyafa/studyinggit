# GitHub: Version Control & Collaboration
#### Syntesa Module: Software Development, Git

<details>
  <summary><b>⚠️ Preview ⚠️</b></summary>
  
#### i. Material list
1. Local Git introduction
2. Cloud GitHub Introduction
3. Basic GitHub command
4. Staging
5. Branching
6. Merge Branch
7. Handling Merge Conflict
8. Pull Request & Code Review Workflow

#### ii. Goals
To understand...
- What is version control & how to collaborate.
- Why we need version control & to collaborate.
- The terms inside version control
- How to use Git
- How to use GitHub

(the materials will be heavily referenced from [w3schools.com](https://www.w3schools.com/git/)
</details>

## I. What is Git?
A version control system. Created by LInux Trovalds in 2005, and he after he found someone that can maintain this second project of his, he throws it into Junio Hamano.

It is used for:
- Tracking code changes
- Tracking who made changes
- Coding collaboration



<details>
<summary><b> ‼️ Key Concepts ‼️ </b></summary>

#### 1. Key Computer Storage / Data mgmgt. Concepts
Before entering,let's assume that...
| Terms | Means |
| ----- | ----- |
| **Machine** | (or device) are your computer, laptop, phone, is a machine, powered by electricity |
| **Local** | Device that you interact physically |
| **Server** | Another computer, but it's optimized to *serve* data to toher computers over a network or the internet |
| **Remote** | Device that you interact remotely (from far away) |
| **Localhost** | A nickname your computer uses to talk to itself |
| **CLI** | Command Line Interface/Terimnal, text-only window where you type commands to talk direclty to your operating system (OS) |
| **Directory** | How the computer tracks data, while a folder is how you interact with it (about the same thing)|
| **Metadata** | Data about data, like how .jpg have information like camera model, GPS coordinate, file size, etc. |

#### 2. Key Git Concepts
For understanding Git, one must understand...
| Terms | Means |
| ----- | ----- |
| **Repository** | A folder where Git tracks your project and its history |
| **Clone** | Make a copy of a remote repository on your device |
| **Stage** | Tell Git which changes you want to save next |
| **Commit** | Save a snapshot of your staged changes |
| **Branch** | Work on different versions or features at the same time |
| **Merge** | Combine changes from different branches |
| **Pull** | Get the latest changes from a remote repository |
| **Push** | Send your changes to a remote repository |

</details>

#### Working with Git
- *Initialize* or running Git for the first time on a folder, making the folder a **Repository**
- Git now creates a hidden folder to keep track of changes in that folder ```(e.g. /Folder/.git/)```. As if it is your project's metadata.
- When a file is changed, added or deleted, it is considered **modified**
- You select the modified files you want to **Stage**
- the **Staged** files are **Committed**, which prompts Git to store a **permanent** snapshot of the files
- Git allows you to see the full history of every commit
- **You can revert back** to any previous commit
- Git **does not store a separate copy of every file in every commit** (otherwise it will loads up your storage in no time), but keeps track of changes made in each commit

<details>
  <summary>
    <b>Git Setup (Install -> Configure) </b>
  </summary>

## II. Git Setup
To get started, one must install it first as it is not come by your system by default probably.

### 1. Git Install
  
<details>
  <summary>
    <b>
     😈 Windows 😈
    </b>
  </summary>
  <br>

1. Download Git in Microsoft Store or the [official website](https://git-scm.com/install/windows)
2. Run the installer
3. Click "Next" to accept the recommended settings.
4. This will install Git and Git Bash (mini-*Linux*-sytle emulator, that lets Windows Machine run standard Linux commands)
  
</details>

<details>
  <summary>
    <b>
     🍎 MacOS 🍎
    </b>
  </summary>
  <br>

1. If you use Homebrew, Open Terminal
2. run ```brew install git```
3. Or, download the *Note:** Git is case-sensitive when it comes to file names on certain operating systems.```.dmg``` file and drag Git to your Applications folder.

</details>

<details>
  <summary>
    <b>
      🐧 Linux 🐧
    </b>
  </summary>
  <br>

1. Open Terminal and use your package manager
2. Install Git
- for Ubuntu/Debian based: ```sudo apt-get install git```
- for Arch based: ```sudo pacman -S git ```
- for Red Hat based: ```sudo dnf install git```
- for openSUSE: ```sudo zypper install git```
- for Alpine: ```apk add git```
  
</details>

### 2. Verifying Instalation
Open GitBash if you're on Windows or Terminal if you're on Linux/MacOS, check that Git works by opening your terminal) by running:

> [!TIP] 
> ```git --version```

and it should return your git version e.g. ```git version 2.5x.x```

### 3. Add Git to PATH after installation

<details>
  <summary>
    <b>
      Windows
    </b>
  </summary>
<br>
  
1. If you missed the option during installation, search for ```Environment Variables``` and find the **Path** variable under ```System variables```.
2. click Click ```Edit```, then ```New```, and add the path to your Git ```bin``` and ```cmd``` folders (e.g., ```C:\Program Files\Git\bin and C:\Program Files\Git\cmd```).
3. Click OK to save. Restart your terminal.

</details>

<details>
  <summary>
    <b>
      MacOS & Linux
    </b>
  </summary>
<br>
  
1. Using Homebrew (Mac) or Package managers (Linux) usually automatically adds Git to Path automatically.
2. If not, open terminal and add this line to your ```terminal config file```:
```
   export PATH="/usr/local/bin:$PATH" # MacOS
   export PATH="/usr/bin:$PATH" # Linux
   ```
3. Save the file and run ```source ~/<your-config-file-dir>```

After adding Git to your PATH, open a new terminal window and run ```git --version``` to check that it works **everywhere**.
</details>

### 4. Updating or Uninstalling Git
By using package manager
- ```brew update git```
- ```sudo apt-get upgrade git``` or any other package manager...
- or download and run the latest installer

<details>
  <summary>
    <b>
     🔧 Troubleshooting Git Installation 🔧
    </b>
  </summary>
  <br>

- ```"git is not recognized as an internal or external command"```
  - **Solution**: Git is not in your system's ```PATH```. Make sure you installed Git and restart your terminal.
  - If needed, add Git's bin folder ```(usually C:\Program Files\Git\bin)``` to your ```PATH```.
  - If it still doesn't work, try restarting your computer.

- ```Permission errors ("Permission denied")```
  - Solution: On Windows, run Git Bash or your terminal as administrator.
  - On macOS/Linux, use sudo if necessary.

- ```SSL or HTTPS errors when cloning/pushing```
  - **Solution**: Check your internet connection.
  - Make sure your Git version is up to date.

- ```Wrong version of Git```
  - **Solution**: Check your installed version with ```git --version.```
  - Download the latest version from the official website if needed.

</details>

### 5. Configure Git

>[!Warning]
> - System (all users): ```git config --system```
> - Global (current user): ```git config --global```
> - Local (current repo): ```git config --local```

#### 5.1. Name
Your name will be attached to your commits. Set it with:
```
git config --global user.name "your-name"
```

#### 5.2. Email
Your email is also attached to your commits. Set it with:
```
git config --global user.email "you@example.com"
```

#### 5.3. Branch Name
Set the default branch name for new repositories (for example, ```main``` instead of ```master```):
```
git config --global init.defaultBranch main
```

>[!TIP]
>run ```git --help``` for further commands

</details>

<details>
  <summary>
    <b>Git Init -> Stash</b>
  </summary>

## III. Get Started with Git
Create a project folder, navigate to the folder, and initialize a Git repository.

### 1. Creating Git Folder
#### 1.1. make the folder (creates a new directory)
```
mkdir myproject
```
#### 1.2.navigate to the folder (changes the current working directory)
```
cd myproject
```
#### 1.3. Initialize Git
```
git init
```
After running that there will be hidden ```.git``` folder inside that repository.

### 2. New File
Make any file, e.g. ```test.txt``` file and save it into the repository. Example by running this in terminal 
```
echo "Hi, i'm testing Git" > test.txt
```
#### 2.1. Check file status
 - To see which files are in your project folder, use the ```ls``` command.
 - To see which files are tracked, use ```git status``` command.

>[!TIP]
>**Untracked file** is any file in your project that Git is not yet tracking. You've created or copied into the folder, but haven't *told* Git to watch.
>**Tracked file** is a file that Git is watching for changes. To make a file tracked, you need to add it to the staging area.

#### 2.2. Stage a File
- To add a file to the staging area, use ```git add <file>```:
```
git add test.txt
```
Now test.txt is staged. You can check what is staged with ```git status```.

- To remove file from the staging area (unstage it) run:
```
git restore --staged test.txt
```
Now ```test.txt``` is no longer staged. You can also use ```git reset HEAD index.html``` for the same effect.

### 3. Commit
>[!TIP]
> - ```git commit -m "message"``` - Commit staged changes with a message
> - ```git commit -a -m "message"``` - Commit all tracked changes (skip staging)
> - ```git log``` - See commit history

To save your staged changes, use:
```
git commit -m "your message"
```

You can skip the staging step for already tracked files with 
```
git commit -a -m "message".
```
This commits all modified and deleted files, but not new/untracked files.

>[!WARNING]
>Skipping the staging step can make you include unwanted changes. Use with care.
>```git commit -a``` does not work for new/untracked files. You must use ```git add <file>``` first for new files.

If you just type ```git commit``` (no ```-m```), your default editor will open so you can write a detailed, multi-line message.

>[!TIP]
> Best Practice for Commit Message:
> - Keep the first line short (50 characters or less).
> - Use the imperative mood (e.g., "Add feature" not "Added feature").
> - Leave a blank line after the summary, then add more details if needed.
> - Describe why the change was made, not just what changed.

#### 3.1. Commit Hitory
To view the history of commits for a repository, you can use:
```
git log
```

For a shorter view, use ```git log --oneline```
To see which files changed in each commit, use ```git log --stat```

### 4. Tag
A **tag** in Git is like a label or bookmark for a specific commit.
Tags are most often used to mark important points in your project history, like releases (**v1.0** or **v2.0**).

>[!TIP]
> - ```git tag <tagname>``` - Create a lightweight tag
> - ```git tag -a <tagname>``` -m "message" - Create an annotated tag
> - ```git tag <tagname> <commit-hash>``` - Tag a specific commit
> - ```git tag``` - List tags
> - ```git show <tagname>``` - Show tag details

Tags are a simple and reliable way to keep track of versions and share them with your team or users.

Some common tag types include:
- **Releases**: Tags let you mark when your project is ready for release, so you (and others) can always find that exact version later.
- **Milestones**: Use tags to highlight major milestones, like when a big feature is finished or a bug is fixed.
- **Deployment**: Many deployment tools use tags to know which version of your code to deploy.
- **Hotfixes**: If you need to fix an old version, tags make it easy to check out and patch the right code.

>[!TIP]
> - Use tags to mark releases, major milestones, or stable points in your project.
> - Always use annotated tags (with -a -m) for anything public or shared.
> - Create tags after passing all tests or before deploying/releasing code.

### 5. Stash
Sometimes you need to quickly switch tasks or fix a bug, but you're not ready to commit your work.
```git stash``` lets you save your uncommitted changes and return to a clean working directory.
You can come back and restore your changes later.

Here are some common use cases:
- **Switch branches safely**: Save your work before changing branches.
- **Handle emergencies**: Stash your work to fix something urgent, then restore it.
- Keep your **work-in-progress safe**: Avoid messy commits or losing changes.

>[!TIP]
> - **Tracked files** (both staged and unstaged) are stashed by default.
> - **Untracked files** (new files not yet added to Git) are not stashed by default.
> - To stash untracked files too, use ```git stash -u``` (or ``--include-untracked```).

</details>

<details>
  <summary>
    <b>History -> Merging</b>
  </summary>


## III. History, Branching, Merging

### 6 Git History
Git keeps a detailed record of every change made to your project. This is useful for tracking progress, finding bugs, and understanding your project's evolution.

>[!TIP]
> - ```git log``` - Show full commit history
> - ```git log --oneline``` - Show a summary of commits
> - ```git show <commit>``` - Show details of a specific commit
> - ```git diff``` - See unstaged changes
> - ```git diff --staged``` - See staged changes

#### 6.1. Compare Two Commits
See what changed between any two commits
```
git diff <commit1> <commit2>
```

#### 6.2. Show a Branch Graph
See a simple ASCII graph of your branch history (great for visualizing merges)
```
git log --graph --oneline
```

#### Git Branch
In Git, a ```branch``` is like a separate workspace where you can make changes and try new ideas without affecting the main project. Think of it as a "parallel universe" for your code.

>[!WARNING]
>Common reasons to create a branch
> - Developing a new feature
> - Fixing a bug
> - Experimenting with ideas

To list how many branches do your project has
```
git branch
```
By default it should only be ```main``` or ```master``` with the ```*``` which means you are currenlty on that ```branch```

Create new ```branch```:
```
git branch <new-branch-name>
```




</details>
