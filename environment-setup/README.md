# Installfest Step 1: Development Environment Setup

## Operating System & Command Line Tools

If you don't already have an account for the Mac App Store, follow the instructions on Apple Support to <a href="https://support.apple.com/kb/PH11499?locale=en_US" target="_blank">create a Mac App Store account</a>.

Before class starts, we suggest you upgrade your operating system to OS X Yosemite (10.10), OS X El Capitan (10.11), or macOS Sierra.  If you're on an older machine with 4GB or less of memory, please stick to OS X Yosemite.  Also, if Apple releases a newer version of macOS while you're in WDI; please don't update until your instructors say it's ok.

To check which operating system you're running:

1. Click the apple icon in the top left of your computer screen.
2. Select "About This Mac" from the dropdown menu.
3. Read the version information from the window that pops up.

If you are not using OS X Yosemite (10.10), OS X El Capitan (10.11), or macOS Sierra, detailed instructions for upgrading your operating system are available through Apple support: <a href="https://support.apple.com/macos" target="_blank">How to upgrade to macOS Sierra</a>.  

> Please let an instructor know if you're using an older version of OS X or if your system has less than 2 GB of memory.

### Install Command Line Tools from the Terminal

1. Open the Terminal application.  If you need to find it, try the keyboard shortcut Command + Space, which will bring up spotlight so you can search for Terminal.
2. In your Terminal, type `xcode-select --install`, and a new window and installer will appear.
3. Follow the instructions in the installer.

### Install Command Line Tools through Xcode (Older Versions of OS X)

**Only follow these steps if you were not able to install Xcode Command Line Tools with the instructions above.** If you must run an older version of OS X, you will need to install Command Line Tools that come from Xcode.

1. Open the Mac App Store and install Xcode.
2. Open Xcode.
3. Inside the Xcode menu, choose Preferences > Downloads > Install The Command Line Tools.
4. Follow the instructions in the installer.

## Homebrew

__Note:  when copying the code snippets, please exclude the `$` as you paste and run the code into your terminal.  The dollar sign `$` is simply an indicator of the logged-in user in examples.__

<a href="http://brew.sh" target="_blank">Homebrew</a> is a *package manager* - it downloads and updates programs on your machine. We'll use it to quickly download and install other tools we need, or to update already installed tools.

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
    $ echo 'export PATH="/usr/local/bin:/usr/local/sbin:~/bin:$PATH"' >> ~/.bash_profile
    ```

6. Let's install our first package with Homebrew!  
  <!-- The `tree` package adds a command to your Terminal that displays files in a tree view (instead of a list view like `ls`).  Enter the following command in your Terminal:

    ```bash
    $ tree
    ```
  It will tell you that this command is not found or it just won't do anything. This is because it's not a program (command) that's installed on your machine. Now install it with this command:

    ```bash
    $ brew install tree
    ```

7. Now run the Terminal command `tree` to see a tree view of all the files inside your current directory!
 -->
7. `trash` is a Homebrew package that easily allows one to move files or folders into the trash bin from the terminal. This is good practice because [other commands](http://docstore.mik.ua/orelly/unix3/upt/ch14_03.htm) may be more dangerious. Again, the `trash` tool does not permanently delete files or folders, but simply places them in the trash. Let's install it using homebrew with the command:

    ```bash
    $ brew install trash
    ```

8. We can test this by creating a file and moving our dummy file into our trash bin. Run these lines in your terminal to see the power of `trash`:

    ```bash
    $ touch new-trash-file.txt
    $ ls
    ```

    You should see the newly created file.

    ```
    $ trash new-trash-file.txt
    $ ls
    ```

    Now it's moved to the trash bin!

## Customization


### Styles

If you haven't done anything to personalize the terminal yet, it's probably a little harder to read than it needs to be. We recommend adding some styles to the bash shell. [Solarized](http://ethanschoonover.com/solarized) is a great theme for this purpose.

1. [Download](http://ethanschoonover.com/solarized/files/solarized.zip) the zip file of all the themes.
2. Unzip it by double-clicking.
3. Open your the Terminal Application and navigate to `Terminal` -> `Preferences`. In the bottom left hand corner, find the icon that looks like a cog/gear and select `Import...`.
4. Navigate to the unzipped solarized directory and navigate into the sub-directory `osx-terminal.app-colors-solarized` and select `Solarized Dark ansi.terminal`.
5. Finally, back in the Terminal settings, select Solarized Dark again and click the button `Default` next to the cog/gear icon, which will set this to your default theme.

Try opening up a new window for the Terminal and ensure the color scheme has been updated.  You can play around with other themes or settings through Terminal > Preferences if you like.


<!-- 
### Option as Meta Key

Let's change a setting in the Terminal that will allow us to move through and delete entire words at a time by holding down the `option` key. This the default behavior of most text editors and will allow us to make more productive edits to our bash commands.

1. Navigate back to `Terminal` -> `Preferences`.
2. Navigate to the the sub-tab, `Keyboard`
3. Check the input, at the bottom, that displays "Use Option as Meta key".

Try typing something in the Terminal then using the arrows to navigate through the text; now hold the `option` key at the same time to see the cursor jump from one word to the next. 
-->

### Silent Clicking

In more recent models of Apple computers, the trackpad produces an artifical "click" sound; however, we can turn this off.

1. Navigate to `System Preferences` (try using Command + Space to bring up a search bar), then click `Trackpad`.
2. Navigate to the tab `Point & Click`.
3. At the bottom, check the input that displays "Silent clicking".

Ensure the trackpad no longer makes a noise when clicked.


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

Clarifying notes for the GitHub's instruction that might be confusing:

1. When you are "Adding a new SSH key to your GitHub Account" the command:

	```bash
	$ pbcopy < ~/.ssh/id_rsa.pub
	```

	Will take your SSH key that was saved to the file id_rsa.pub and copy it to your clipboard (similar to using your quick keys cmd C but with the command line).


## Next Up
* [ ] [Set up your Node.js environment](node-express-stack.md)
* [ ] Set up your Ruby environment
* [ ] Install Development Tools
