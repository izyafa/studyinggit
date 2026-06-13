# GitHub: Version Control & Collaboration
#### Syntesa Module: Software Development, Git
## Preview
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

## What is Git?
A version control system. Created by LInux Trovalds in 2005, and he after he found someone that can maintain this second project of his, he throws it into Junio Hamano.

It is used for:
- Tracking code changes
- Tracking who made changes
- Coding collaboration

<details>
<summary><b> ‼️ Key Concepts ‼️ </b></summary>

#### Key Computer Storage Concepts
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
