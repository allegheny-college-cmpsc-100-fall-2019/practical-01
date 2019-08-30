# CMPSC 100-03 Practical Session 1

In this practical session, we focus on setting up various tools and platforms that are mission-critical to our work. Initially, these include:
* [Slack](https://www.slack.com)
* [GitHub](https://www.github.com)
* Chocolatey (**Windows only**)
* [git](https://git-scm.com/downloads)
* [Docker](https://www.docker.com)
* [Atom](https://atom.io)

## General guidelines for practical sessions

* **Experiment!** We design practical sessions to create a space for you to _try things_. Given the expertise of our classroom TLs and my interest in fixing stuff, I am sure that even if something breaks, we can fix it.
* **Complete _something_.** Grading for practical assignments hinges on _completion_. As long as you provide a good faith effort to finish a task, your grade should reflect your effort.
* **Practice skills.** If you work in the discipline of computer science, many of the skills you revisit or establish here are industry standard practice. Learning and practicing them often helps prepare you for either other classes or professional work.
* **Try to finish during the class session** While I provide extra time to complete the work, these assignments can be completed in 50 minutes. This will help you develop your awareness and management of time.
* **Help one another!** We're a community of users here, not competitors. If you grasp something quickly, but a neighbor does not, offer to help them after they've tried for a bit. Conversely, _ask for help_ from either me, our lab TLs, or your neighbor.

## Table of Contents

* [Slack](#slack)
* [GitHub](#github)
* [Chocolatey](#chocolatey-windows-only) (**Windows only**)
* [Securing your GitHub account (SSH)](#securing-your-github-account)
* [Docker](#docker)
* [Running your first container](#running-your-first-container)
* [Atom](#atom)

## Your assignment

Broadly, this practical session's goals are:
* To download and install Atom, a common text editor for software development
* To set up secure communication between your PC and the GitHub platform using a git client
* To prepare your PC for future assignments arriving from [GitHub Classroom](https://classroom.github.com)
* To install the "containerization" platform, Docker
* To run your first "container," proving that your install of Docker is functional

### Slack

A communications platform curing the headache of email.

- [ ] If you have not already, accept my invitation to [Slack](https://www.slack.com).

- [ ] Log in to our [Slack workspace](https://cmpsc100fall2019.slack.com)
- [ ] Navigate to the `#practicals` channel.
* If you did not receive an invitation, let me know and I can send it again.
* **Note**: You can use the `#practicals` channel to discuss various elements of the assignment. In addition you can directly message me (@dluman) to chat directly about questions or issues that you have.

### GitHub

A kind of social network for code and developers to share and comment on code projects.

#### If you do not already have a GitHub account

- [ ] Visit [GitHub](https://www.github.com)
- [ ] Create an account using your @allegheny.edu email
- [ ] When creating a username, pick one which is the same as your Allegheny account username. If the username is taken, you may try substituting underscores for spaces, or adding a digit to the end of the name.

* Once you've completed the above steps, continue with the steps below.

#### If you have a GitHub account

- [ ] Log in to GitHub.
- [ ] In our Slack `#practicals` channel, type the following on **one** line:
* Your name
* Your Allegheny email address
* Your GitHub username

* If you have a bit of time, consider:
    * Adding a professional profile picture to your account
    * Downloading [GitHub's "Student Developer Pack"](https://education.github.com/pack)

* **Note**: Keep your GitHub browser window open; you will use it later

### Chocolatey (Windows only)

* If you aren't a Windows user, you can skip to [git](#git)

Chocolately adds Unix-like commands to the Windows command prompt. Many of these commands are helpful for making your work more efficient and easier.

- [ ] Open a Command Prompt window with administrative privileges
    * You may need to find and right click the `Command Prompt` entry in the start menu, and select `Run as Administrator`
- [ ] Copy and paste the following command:
```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```
- [ ] To test this step, open a new Command Prompt window (`CTRL` + `R`, type `cmd` in the "Run" window) and hit `Enter`), and type:
```
choco --version
```
* You should see a line similar to `Chocolatey v0.10.15`. This indicates that the install was successful.

### git

Whereas GitHub is a kind of social network, git is the application that allows you to make your code available.

#### Opening a terminal window

- [ ] Open a "terminal" window.
* Depending on your operating system there are several ways to do this:
   * **Windows**
       * Press `CTRL` + `R`
       * Type `cmd` in the window that results.
   * **Mac**
       * Press `CTRL` + `OPTION` + `SHIFT` + `T`
   * **Unix**
       * Generally, `CTRL` + `ALT` + `T` does the trick

#### Windows

- [ ] Copy and paste the following command:
```
choco install git -y --params "/GitAndUnixToolsOnPath /WindowsTerminal /NoShellIntegration"
```
- [ ] After this operation completes, type `git --version` in the terminal window.
* If a line similar to `git version 2.23.0.windows.1` appears, the installation was successful.

#### Mac

- [ ] In a terminal, type `git --version`
* If git is not yet installed, the installer will start.

#### Unix

- [ ] In a terminal window, type `sudo apt-get install git`
* If git is not yet installed, the installer will start.

### Securing your GitHub account

The professional world uses a standard object known as an SSH key to prove a given user's identity and encrypt communications.

#### Generating a key

- [ ] In the resulting terminal window based on the steps above, type `ssh-keygen -t rsa -b 4096 -C "YOUR ALLEGHENY EMAIL"` and press `Enter`
- [ ] At the prompt `Enter file in which to save the key`, press `Enter` to accept the default location
* To what location did the function save the key? How do you know? Discuss with a neighbor, a TL, or the professor.
- [ ] At the next prompt, enter a password used to secure the key
* You will use this passphrase to identify yourself as an owner or user of the key
- [ ] Once the keygen has finished, located the `id_rsa.pub` file where the process saved the key
* This is your unique key; it will be unintelligible to you, but it is your unique identifier. Keep all of the files this program generates.
- [ ] In the terminal window, type `cat ~/.ssh/id_rsa.pub`
- [ ] Copy only the portion containing letters and numbers
- [ ] In the browser window containing GitHub, click the uppermost-right icon to access your account menu
- [ ] Locate and click the `Settings` entry
- [ ] On the resulting screen, locate and click the option for `SSH and GPG keys`
- [ ] Click `New SSH key`
- [ ] Give the key a title such as `Allegheny CS`
- [ ] Paste the long string of letters and numbers you copied above into the `Key` field
- [ ] Click `Add SSH key` to add the key

### Docker

Docker is what is referred to as a "containerization" platform. Essentially, it is software  which ensures that programs run the same way _everywhere_. Docker is developed with the same goal as that of the Java language we'll learn in this course--that software should work the same regardless of where it's run. Our Docker "images" will contain a single, standard Unix (Ubuntu) operating system. This minimizes technical issues and allows developers to concentrate on their code, rather than system specs. Instead of downloading dozens of tools to build and execute software, containers allow us to run one file containing all of the utilities necessary.


- [ ] Download and install Docker.
* Depending on your operating system's version, you may need a specific platform. Consult your OS when considering the following options:
    * **Windows 10 Pro or Enterprise**: [https://download.docker.com/win/stable/Docker for Windows Installer.exe](https://download.docker.com/win/stable/Docker%20for%20Windows%20Installer.exe)
    * **Mac OS X > 10.11**: [https://download.docker.com/mac/stable/docker.dmg](https://download.docker.com/mac/stable/docker.dmg)
    * **Unix**: Depending on your version, use `apt` or `yum` (or other package manager)
    * **Older versions of Windows and Mac** (Windows 10 Home or Mac OS X 10.11 or earlier):
        * For reasons which we can discuss as the need arises, older versions of Windows and Mac OS need to use other software known as "Docker Toolbox"
        * Follow the instructions to install [Docker Toolbox](https://docs.docker.com/toolbox/toolbox_install_windows) to download.
        * **Note**: During installation, the installer screen may feature an option to install Oracle VirtualBox. Be sure to place a check mark by this option or click "Yes" at the resulting prompts which ask to run Oracle VirtualBox.
        * If you already completed the steps installing git for your device, uncheck the "Git for Windows" option in the installer.
        
#### If you installed "Docker Desktop"
- [ ] Once you've loaded Docker open a terminal window (refer to the [section above](#securing-your-github-account) for terminal instructions).
- [ ] In the terminal window, type `docker --version`.
    * The terminal should display a line similar to `Docker version 19.03.1, build 74b1e89`
    * If not, let either the professor or a TL know.

#### If you installed "Docker Toolbox"
- [ ] Locate the "Docker Quickstart Terminal" and open it.
    * This should open a terminal window. If it doesn't let either the professor or a TL know.
- [ ] In the terminal window type `docker --version`
    * You should receive a line similar to `Docker version 19.03.1, build 74b1e89`.
    * If not, let either the professor or a TL know.
    
### Running your first container

A "container," though a techical term here, is pretty much what it sounds like: a sealed package that, while "renting" space on your hard drive, acts as an isolated set of software, usually containing an operating system and other specialized applications necessary for a specific task. Typically, these operating systems and software combinations are _as spare as possible_, meaning that (to conserve "weight" or "footprint") they only incorporate exactly what they need to run and nothing more.

The "Hello, World" is a well-established computer science tradition. Often, when learning a new language or technology, the first example that a user makes is called a "Hello, World." This Docker container contains only enough to run this example, the output of which is highlighted below.

- [ ] In a terminal (Docker Quick Start Terminal for `Docker Toolbox`) window, type `docker run hello-world`.

* This command will download and run the "Hello, World" container, returning output looking similar to the following:

```
docker run hello-world
docker : Unable to find image 'hello-world:latest' locally
...
latest:
Pulling from library/hello-world
ca4f61b1923c:
Pulling fs layer
ca4f61b1923c:
Download complete
ca4f61b1923c:
Pull complete
Digest: sha256:97ce6fa4b6cdc0790cda65fe7290b74cfebd9fa0c9b8c38e979330d547d22ce1
Status: Downloaded newer image for hello-world:latest
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

### Atom

- [ ] Visit [https://atom.io](atom.io) to download the installer for your operating system.

## Submitting this assignment

To submit this assignment, navigate to the `#practicals` channel in our class Slack [https://cmpsc100fall2019.slack.com](https://cmpsc100fall2019.slack.com) and type:
* The operating system of your machine
* Which of the installs completed successfully.
* Which of the installs did not complete (or you did not get to)
* A short description of your experience completing this practical session.