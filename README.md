# CMPSC 100-03 Practical Session 1

In this practical session, we focus on setting up various tools and platforms that are mission-critical to our work. Initially these include:
* [git](https://git-scm.com/downloads)
* [GitHub](https://www.github.com)
* [Docker](https://www.docker.com)
* [Slack](https://www.slack.com)

## General guidelines for practical sessions

* **Experiment!** We design practical sessions to create a space for you to _try things_. Given the expertise of our classroom TLs and my interest in fixing stuff, I am sure that even if something breaks, we can fix it.
* **Complete _something_** Grading for practical assignments hinges on _completion_. As long as you provide a good faith effort to finish a task, your grade should reflect your effort.
* **Practice skills** If you work in the discipline of computer science, many of the skills you revisit or establish here are industry standard practice. Learning and practicing them often helps prepare you for either other classes or professional work.
* **Try to finish during the class session** While I provide extra time to complete the work, these assignments can be completed in 50 minutes. This will help you develop your awareness and management of time.
* **Help one another!** We're a community of users here; not students in competition for grades. If you grasp something quickly, but a neighbor does not, offer to help them after they've tried for a bit. Conversely, _ask for help_ from either me, our lab TLs, or your neighbor.

## Your assignment
Broadly, this practical session's goals are:
* To set up secure communication between your PC and the GitHub platform using a git client
* To prepare your PC for future assignments arriving from [GitHub Classroom](https://classroom.github.com)
* To install the "containerization" platform, Docker
* To run your first "container," proving that your install of Docker is functional

### Slack

A communications platform curing the headache of email.

- [ ] Accept my invitation to [Slack](https://www.slack.com).
- [ ] Log in to our [Slack workspace](https://cmpsc100fall2019.slack.com)
- [ ] Navigate to the #practicals channel.
* If you did not receive an invitation, let me know and I can send it again.
* **Note**: You can use the #practicals channel to discuss various elements of the assignment. In addition you can directly message me (@dluman) to chat directly about questions or issues that you have.

### GitHub

A kind of social network for code and developers (aka the community of nerds of which you are now a de facto member).

#### If you do not already have a GitHub account

- [ ] Visit [GitHub](https://www.github.com)
- [ ] Create an account using your @allegheny.edu email
- [ ] When creating a username, pick one which is the same as your Allegheny account username. If the username is taken, you may try substituting underscores for spaces, or adding a digit to the end of the name.

* Once you've completed the above steps, continue with the steps below.

#### If you have a GitHub account

- [ ] Log in to GitHub.
- [ ] In our Slack #practicals channel, type one **one** line:
* Your name
* Your Allegheny email address
* Your GitHub username

* **Note**: Keep your GitHub browser window open; we will use it later

### git

Whereas GitHub is the social network, git is the "share button" that allows you to make your code available so that we can all nerd out about code. It's fun, I promise.

- [ ] Visit the [git](https://git-scm.com/downloads) to download the version of git for your operating system (O.S.).

### Securing your GitHub account

The professional world uses a standard object known as an SSH key to prove a given user's identity and encrypt communications for only those cool enough to read them (AKA have keys which allow them to log in to a server). This is your magic decoder ring.

- [ ] Open a "terminal" window.
* Depending on your operating system there are several ways to do this:
   * **Windows**
       * Click Start > Run (or press `CTRL` + `R`) to print up the "Run" window.
       * Type `cmd`
   * **Mac**
       * Press `CTRL` + `OPTION` + `SHIFT` + `T`
   * **Unix**
       * Generally, `CTRL` + `ALT` + `T` does the trick
- [ ] In the resulting terminal window based on the steps above, type `ssh-keygen` and press `Enter`
- [ ] At the prompt `Enter file in which to save the key`, press `Enter` to accept the default location (indicated in the parenthesis in the line)
- [ ] At the next prompt, enter a password used to secure the key
* You will use this passphrase to identify yourself as an owner or user of the key
- [ ] Once the keygen has finished, located the `id_rsa.pub` file where the process saved the key
* This is your unique key; it will be unintelligible to you, but computers read this stuff for fun
- [ ] Open the `id_rsa.pub` file in a text editor (Notepad, et al.)
- [ ] Copy only the portion the letters and numbers of the key
- [ ] In the browser window containing GitHub, click the uppermost-right icon to access your account menu
- [ ] Locate and click the `Settings` entry
- [ ] On the resulting screen, locate and click the option for `SSH and GPG keys`
- [ ] Click `New SSH key`
- [ ] Give the key a title such as `Allegheny`
- [ ] Paste the long string of letters and numbers you copied above into the `Key` field
- [ ] Click `Add SSH key` to add the key

### Docker

Docker is what is referred to as a "containerization" platform. Essentially, it is software (like the programming language we'll use in the course, Java), which ensures that programs run the same way _everywhere_. Our Docker "images" will contain a single, standard Unix (Ubuntu) operating system. This minimizes technical issues and allows developers to concentrate on their code, rather than system specs.

* When you get to this step in the practical, get the attention of either the professor or class TLs before proceeding.

- [ ] Download and install Docker.
* Depending on your operating system's version, you may need a specific platform. Consult your OS when considering the following options:
    * **Windows 10**: [https://download.docker.com/win/stable/Docker for Windows Installer.exe](https://download.docker.com/win/stable/Docker%20for%20Windows%20Installer.exe)
    * **Mac**: [https://download.docker.com/mac/stable/docker.dmg](https://download.docker.com/mac/stable/docker.dmg)
    * **Unix**: Depending on your version, use `apt` or `yum` (or other package manager)
    * **Older versions of Windows and Mac** (Windows 10 Home or Mac OS X 10.11 or earlier):
        * For reasons which we can discuss as the need arises, older versions of Windows and Mac OS need to use other software known as "Docker Toolbox"
        * Follow the instructions to install [Docker Toolbox[(https://docs.docker.com/toolbox/toolbox_install_windows](https://docs.docker.com/toolbox/toolbox_install_windows) to download.
        * **Note**: During installation, the installer screen may feature an option to install Oracle VirtualBox. Be sure to place a check mark by this option or click "Yes" at hte resulting prompts which ask to run Oracle VirtualBox.