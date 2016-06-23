## Sublime Text Editor

1. Use this link to <a href="http://c758482.r82.cf2.rackcdn.com/Sublime%20Text%20Build%203083.dmg" target="_blank">download Sublime Text 3</a>.
    * Sublime Text 3 is FREE, as in _you don't need to pay for it_.
2. Open the downloaded file.
3. Follow the installation instructions (drag Sublime Text 3 to your Applications folder).
4. Open the Sublime Text 3 application.

### Configure Tab Size
We encourage you to set your tab size to 2 spaces:

1. In the menu bar, click: `Sublime Text 3` > `Preferences` > `Settings - User`
2. Replace the existing text with the following configuration options:

    ```json
    {
        "tab_size": 2,
        "translate_tabs_to_spaces": true
    }
    ```

### Add Package Control
Sublime Text 3's core functionality can be extended using [thousands of third-party packages](https://packagecontrol.io/) that can help reduce your errors, and increase your productivity.

To get started, we need to install `Package Control`:

1. Follow <a href="https://packagecontrol.io/installation" target="_blank">Package Control's "simple installation" instructions</a> to add Package Control to Sublime Text 3. (When you paste the large block of text, make sure you enter the text into the bottom rectangle of the Sublime Text console).
2. We access Package Control through the Sublime Text command palette. Open the palette by pressing `cmd + shift + p` within Sublime Text. Start typing "Package Control" in the command palette to see the list of things Package Control can do.

### Add Packages
Now we're ready to install our first packages!

**Package Installation Instructions**: From the command palette (`cmd + shift + p`), select `Package Control: Install Package` to bring up the list of available packages. Simply select/highlight the name of the package to install it (or type the name to search for it)!

Using the above installation process, we recommend you install the following packages:

* [`Emmet`](https://packagecontrol.io/packages/Emmet)

#### Add Linters
Now we're ready to install linting packages in Sublime Text 3. Linting tools allow us to check for mistakes in our code and stick to programming language best practices.

We recommend you install the following linters for Javascript and Ruby (using the same package installation instructions as above):

* [`SublimeLinter`](https://packagecontrol.io/packages/SublimeLinter)
    * [`SublimeLinter-jshint`](https://packagecontrol.io/packages/SublimeLinter-jshint)
    * [`SublimeLinter-ruby`](https://packagecontrol.io/packages/SublimeLinter-ruby)

### Open Sublime from the Terminal

Sublime Text 3 includes a program that launches Sublime from the Terminal. We'll use the `ln` command to link that program to a simple `subl` command.

**Before following these steps**, make sure you downloaded Sublime Text 3, NOT Sublime Text 2. Also make sure you're running Sublime from your Applications folder NOT from the installer (go ahead and eject the installer if you haven't already).

1. To run a program from the Terminal, it needs to be available on your $PATH. The next step assumes `/usr/local/bin` is in your $PATH, so let's check that.  Run the following command from the Terminal to see your current $PATH:

    ```bash
    $ echo $PATH
    ```

2. Run the following command in your Terminal to set up the link:

    ```bash
    $ ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
    ```

3. Type `subl .` in the Terminal, and Sublime Text 3 should open!

### Configure Git to Use Sublime

When you forget to enter a commit message in the Terminal, git opens a text editor and reminds you to add a commit message.

1. Run the following command in the Terminal to configure git to open Sublime Text instead of the default text editor:

    ```bash
    $ git config --global core.editor "subl -w"
    ```
