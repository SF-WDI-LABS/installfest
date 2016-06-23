# Installfest Step 1: Development Environment Setup

## Operating System & Command Line Tools

If you don't already have an account for the Mac App Store, follow the instructions on Apple Support to <a href="https://support.apple.com/kb/PH11499?locale=en_US" target="_blank">create a Mac App Store account</a>.

Before class starts, we suggest you upgrade your operating system to OS X Mavericks (10.9), Yosemite (10.10) or El Capitan (10.11).  If you're on an older machine with 4GB or less of memory, please stick to OS X Mavericks.  Also, if Apple releases a newer version of OS X while you're in WDI; please don't update until your instructors say it's ok.

To check what version of OS X you're running:

1. Click the apple icon in the top left of your computer screen.
2. Select "About This Mac" from the dropdown menu.
3. Read the version information from the window that pops up.

If you are not using Mavericks (10.9), Yosemite (10.10), or El Capitan (10.11), detailed instructions for upgrading your operating system are available through Apple support: <a href="https://www.apple.com/support/osx/upgrade" target="_blank">How to upgrade to OS X Yosemite</a>.  

> Please let an instructor know if you're using an older version of OS X or if your system has less than 2 GB of memory.

### Install Command Line Tools from the Terminal

1. Open the Terminal application.
2. In your Terminal, type `xcode-select --install`, and a new window and installer will appear.
3. Follow the instructions in the installer.

### Install Command Line Tools through Xcode (Older Versions of OS X)

**Only follow these steps if you were not able to install Xcode Command Line Tools with the instructions above.** If you must run a version of OS X before Mavericks, you will need to install Command Line Tools that come from Xcode.

1. Open the Mac App Store and install Xcode.
2. Open Xcode.
3. Inside the Xcode menu, choose Preferences > Downloads > Install The Command Line Tools.
4. Follow the instructions in the installer.

## Homebrew

__Note:  when copying the code snippets, please exclude the `$` as you paste and run the code into your terminal.  The dollar sign `$` is simply an indicator of the logged-in user in examples.__

<a href="http://brew.sh" target="_blank">Homebrew</a> is a *package manager* for OS X. We'll use it to quickly download and install other tools we need, or to update already installed tools.

1. Open the Terminal application, and run `which brew` to check if you have Homebrew installed already. The `which` Terminal command shows where on your computer a program is installed. If it is installed, the Terminal will output a file path. If it is not installed, the Terminal won't output anything.

2. **Only if you do not have Homebrew installed**, run the command below to install Homebrew. Wait while Homebrew downloads and installs.

    ```bash
    $ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    ```

    If you run into problems, you may need to run `rm -rf /usr/local/Cellar /usr/local/.git` and then retry the command above.

3. Run `brew update` to update Homebrew.

4. Run `brew doctor` in your Terminal to check that Homebrew and any current packages are installed correctly. If there are issues, `brew doctor` will list suggestions for how to fix them.  Follow these suggestions one by one. If you're not sure what to do, **ask!**

5. Based on the errors in the step above, you may need to edit your `~/.bash_profile` to include the path to Homebrew if `brew doctor` shows warnings.  If in doubt ask for help here.

    ```bash
    $ bash echo 'export PATH="/usr/local/bin:/usr/local/sbin:~/bin:$PATH"' >> ~/.bash_profile
    ```

6. Let's install our first package with Homebrew, `tree`!  This package adds a command to your Terminal that displays files in a tree view (instead of a list view like `ls`).  Enter the following command in your Terminal:

    ```bash
    $ brew install tree
    ```

7. Run the Terminal command `tree` to see a tree view of all the files inside your current directory!

## Git

You should already have git installed and have an account on GitHub from Fundamentals. If not, sign up for an account on <a href="http://www.github.com" target="_blank">github.com</a>. We'll be using GitHub to track code changes and collaborate on projects.

### Confirm Install

1. To check whether git is installed on your system, run the Terminal command `which git`. The output should be a directory path like `/usr/bin/git`. This is where git is installed on your machine. If you don't see any output, git is not installed on your computer.

2. **Only if you do not have git installed**, run the following command in your Terminal:

    ```bash
    $ brew install git
    ```

### Configure Git

Configuring your git settings will help GitHub track your contributions and to make it easier and smoother to commit changes.

1. Use the following three `git config` commands to configure your git user information and have git "cache" (remember) it. We use the `--global` (or `-g`) option to make the configuration apply to all repositories.

    ```bash
    $ git config --global user.name "YOUR_GITHUB_USERNAME"
    $ git config --global user.email "YOUR_GITHUB_EMAIL_ADDRESS"
    $ git config --global credential.helper cache
    ```

2. Generate a SSH key for GitHub by <a href="https://help.github.com/articles/generating-ssh-keys" target="_blank">following GitHub's instructions</a>. This will allow you to use GitHub from your Terminal without entering your login information every time you push.


## Next Up
* [ ] [Setup your Node.js environment](node-express-stack.md)
* [ ] Setup your Ruby environment
* [ ] Install Development Tools
