## Atom Text Editor

1. Go <a href="https://atom.io/" target="_blank">here</a> and download Atom.
2. Open the downloaded file.
3. Follow the installation instructions.
4. Open the Atom application.

### Add Packages
Atom's core functionality can be extended using [thousands of third-party packages](https://atom.io/packages) that can help reduce your errors, and increase your productivity.

> We can install Atom packages in the Atom settings _menu_, or via the _command-line_.  Since we're learning to be awesome developers now, let's use the command-line!

We recommend you install the following packages. In your Terminal, run:

* `apm install emmet-simplified`

#### Add Linters
Now we're ready to install linting packages in Atom. Linting tools allow us to check for mistakes in our code and stick to programming language best practices.

We recommend you install the following linters for Javascript and Ruby. In your Terminal, run:

```bash
apm install linter
apm install linter-ruby

npm install -g jshint # note this is a node package, not an atom package!
apm install linter-jshint
```

### Configure Git to Use Atom

When you forget to enter a commit message in the Terminal, git opens a text editor and reminds you to add a commit message.

1. Run the following command in the Terminal to configure git to open Atom instead of the default text editor:

    ```bash
    $ git config --global core.editor "atom -w"
    ```
