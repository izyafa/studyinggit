# GitHub: Version Control & Collaboration
#### Syntesa Module: Software Development, Git

<details>
  <summary><b>⚠️ Preview ⚠️</b></summary>
  
#### Material list
1. Local Git introduction
2. Cloud GitHub Introduction
3. Basic GitHub command
4. Staging
5. Branching
6. Merge Branch
7. Handling Merge Conflict
8. Pull Request & Code Review Workflow

#### Goals
To understand...
- What is version control & how to collaborate.
- Why we need version control & to collaborate.
- The terms inside version control
- How to use Git
- How to use GitHub
  
</details>

## What is Git?
A version control system. Created by LInux Trovalds in 2005, and he after he found someone that can maintain this second project of his, he throws it into Junio Hamano.

It is used for:
- Tracking code changes
- Tracking who made changes
- Coding collaboration



<details>
<summary><b> ‼️ Key Concepts ‼️ </b></summary>

#### Key Computer Storage / Data mgmgt. Concepts
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

#### Key Git Concepts
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
- the **Stagesd files are **Committed**, which prompts Git to store a **permanent** snapshot of the files
- Git allows you to see the full history of every commit
- **You can revert back** to any previous commit
- Git **does not store a separate copy of every file in every commit** (otherwise it will loads up your storage in no time), but keeps track of changes made in each commit

## Git Setup
To get started, one must install it first as it is not come by your system by default probably.

### Git Install
  
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

#### Verifying Instalation
Open GitBash if you're on Windows or Terminal if you're on Linux/MacOS, check that Git works by opening your terminal) by running:

> [!TIP] 
> ```git --version```

and it should return your git version e.g. ```git version 2.5x.x```

#### Add Git to PATH after installation

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

#### Updating or Uninstalling Git
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
