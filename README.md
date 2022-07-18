# Shared VS Code snippets 🫱🏼

## The concept

The idea is to check your code snippets into source control so they can be shared with others.

## How to make it work

In order to do this, we must:

1. Create (or clone) a git repo to house the snippets in a part of the file system that we can control (e.g., in our 'projects' directory).

2. Then create a (local) symbolic link connecting our snippets repo to the directory that VS Code looks at for its snippets.


## Creating the link on Mac

Something like:

```
ln -s  /Users/<USER>/<YOUR FOLDER>/vscode-snippets/snippets/   /Users/<USER>/Library/Application\ Support/Code/User/snippets
```


## Creating the link on Windows

Something like:

```
mklink /D  c:\Users\<USER>\AppData\Roaming\Code\User\snippets  c:\<YOUR FOLDER>\vscode-snippets\snippets
```

## ⚠️ What to watch out for!

By default, when you edit a snippet in VS Code for the first time, it creates a new `.json` file in its default snippets directory.  But in our case we're using a directory in a different location as our source-of-truth.  So we may need to be careful when editing the snippets via the normal flow that VS Code provides.  I think we need to make sure it doesn't create snippet files in its default location.

## Resources

See [this article](https://betterprogramming.pub/creating-and-syncing-personal-snippets-in-vs-code-d03a8d441019), particularly, the "syncing" section.
