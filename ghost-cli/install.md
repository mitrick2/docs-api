---
title: "install"
date: "2018-10-01"
meta_title: "Ghost-CLI commands: install - Documentation"
meta_description: "Your one-stop-shop to install a running production instance of Ghost."
next:
  url: "/api/ghost-cli/setup/"
  title: "Setup"
keywords:
    - cli
    - ghost
    - install
    - setup
sidebar: "ghost-cli"
---

The `ghost install` command is your one-stop-shop to get a running production install of Ghost.

This command includes the necessary mysql, nginx and systemd configuration to get your publication online, and provides a series of setup questions to configure your new publication. The end result is a fully installed and configured instance ✨

> Not ready for production yet? `ghost install local` installs ghost in development mode using sqlite3 and a local process manager. Read more about [local installs](/install/local/). 


## How it works

The `ghost install` command runs a nested command structure, but you only ever have to enter a single command. 

First, it will run `ghost doctor` to check your environment is compatible. If checks pass, a local folder is setup, and Ghost is then downloaded from npm and installed.

Next, `ghost setup` runs, which will provide [prompts](/install/ubuntu/#install-questions) for you to configure your new publication via the `ghost config` command, including creating a MySQL user, initialising a database, configure nginx and sets up SSL. 

Finally, the CLI will prompt to see if you want to run Ghost and if you choose yes `ghost start` will run. 

Ta-da 🎉 a single command has successfully installed Ghost. To read more about the full install process for production check out the [setup guide](/install/ubuntu/).


## Arguments

Here are some useful options when using the `ghost install` command: 

```bash
# Install a specific version (1.0.0 or higher)
ghost install [version]

# Install version 2.15.0
ghost install 2.15.0

# Install locally for development
ghost install local

# Install a local copy of Ghost v1 (Useful when upgrading from 0.x)
ghost install local --v1

```

## Options

As `ghost install` runs nested commands, it also accepts options for the `ghost doctor`, `ghost config`, `ghost setup` and `ghost start` commands.

See the individual command docs, or run `ghost install --help` for more detailed information.

```bash
# Get more information before running the command
ghost install --help

# Install in development mode for a staging env
ghost install --development, ghost install -D

# Install latest version of v1
ghost install --v1

# Select the directory to install Ghost in
ghost install --dir path/to/dir
 
# Install Ghost from a specific zip (useful for testing or custom builds)
ghost install --zip path/to/file.zip

# Disable stack checks
ghost install --no-stack

# Install without running setup
ghost install --no-setup

# Install without starting Ghost
ghost install --no-start

# Tells the process manager not to restart Ghost on server reboot
ghost setup --no-enable

# Install without prompting (disable setup, or pass all required parameters as arguments)
ghost install --no-prompt

```

See the [ghost setup](/api/ghost-cli/setup) and [ghost config](/api/ghost-cli/config) command for full options.
