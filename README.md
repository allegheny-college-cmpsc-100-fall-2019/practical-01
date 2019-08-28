# CMPSC 100-03 Practical Session 1
In this practical session, we focus on setting up various tools and platforms that are mission-critical to our work. Initially these include:
* [git](https://git-scm.com/downloads)
* [GitHub](https://www.github.com)
* [Docker](https://www.docker.com)
* [Slack](https://www.slack.com)

## Your Assignment
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

- [ ] Visit the [git](https://git-scm.com/downloads) to download the version of git for your operating system.

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
* You will use this passphrase to identify yourself as an owner or user of the key.
- [ ] Once the keygen has finished, located the `id_rsa.pub` file where the process saved the key
* This is your unique key; it will be unintelligible to you, but computers read this stuff for fun
- [ ] Open the `id_rsa.pub` file in a text editor (Notepad, et al.)
- [ ] Copy only the portion the letters and numbers of the key
- [ ] In the browser window containing GitHub, click the uppermost-right icon to access your account menu
- [ ] Locate and click the `Settings` entry
- [ ] On the resulting screen, locate and click the option for `SSH and GPG keys`
- [ ] Click `New SSH key`
- [ ] Give the key a title such as `Allegheny`
- [ ] Paste the long string of letters and numbers you copied above into the `Key` field.
- [ ] Click `Add SSH key` to add the key.
