---
title: "setup"
date: "2018-10-01"
meta_title: "Ghost-CLI commands: setup - Documentation"
meta_description: "The real magic in the Ghost-CLI is the automated setup process. Find out how to get started with Ghost using a single command"
next:
  url: "/api/ghost-cli/start/"
  title: "Start"
keywords:
    - cli
    - ghost
    - setup
    - install
sidebar: "ghost-cli"
---

`ghost setup` is the real magic in Ghost-CLI. You will probably never need to run it yourself, as it is called automatically by `ghost install`.


## How it works

Setup configures your server ready for running Ghost in production. It assumes the [recommended stack](/install/ubuntu/#prerequisites/) and leaves your site in a production-ready state. 

Setup is broken down into stages:

- **mysql** - create a specific MySQL user that is used only for talking to Ghost's database.
- **nginx** - creates an nginx configuration
- **ssl** - setup SSL with letsencrypt, using [acme.sh](https://github.com/Neilpang/acme.sh)
- **migrate** - initialises the database
- **linux-user** - creates a special low-privilege `ghost` user for running Ghost


## What if I want to do something else?

The `Ghost-CLI` tool is designed to work with the recommended stack and is the only supported install method. However, since Ghost is a fully open-source project, and many users have different requirements, it is possible to setup and configure your site manually. 

The CLI tool is flexible and each stage can be run individually by running `ghost setup <stage-name>` or skipped by passing the `--no-setup-<stage-name>` flag.


## Arguments

```bash
# Run ghost setup with specific stages
ghost setup [stages...]

# Creates a new mysql user with minimal privileges 
ghost setup mysql

# Creates an nginx config file in `./system/files/` and adds a symlink to `/etc/nginx/sites-enabled/`
ghost setup nginx

# Creates an SSL service for Ghost
ghost setup ssl

# Create an nginx and ssl setup together
ghost setup nginx ssl

# Creates a low-privieleged linux user called `ghost`
ghost setup linux-user

# Creates a systemd unit file for your site
ghost setup systemd

# Runs a database migration
ghost setup migrate
```

## Options

As `ghost setup` runs nested commands, it also accepts options for the `ghost config`, `ghost start` and `ghost doctor` commands.

See the individual command docs, or run `ghost setup --help` for more detailed information.


```bash
# Skips a setup stage
ghost setup --no-setup-mysql
ghost setup --no-setup-nginx
ghost setup --no-setup-ssl
ghost setup --no-setup-systemd
ghost setup --no-setup-linux-user
ghost setup --no-setup-migrate

# Configure a custom process name should be (default: ghost-local)
ghost setup --pname my-process

# Disable stack checks
ghost setup --no-stack

# Setup without starting Ghost
ghost setup --no-start

# Tells the process manager not to restart Ghost on server reboot
ghost setup --no-enable

# Install without prompting (must pass all required parameters as arguments)
ghost setup --no-prompt

```

See the [ghost config](/api/ghost-cli/config) command for full options.
