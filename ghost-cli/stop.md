---
title: "stop"
date: "2018-10-01"
meta_title: "Ghost-CLI commands: stop - Documentation"
meta_description: "Stop Ghost from running in the background with a single command using Ghost-CLI. Read more in the official documentation."
next:
  url: "/api/ghost-cli/restart/"
  title: "Restart"
keywords:
    - cli
    - ghost
    - stop
    - install
sidebar: "ghost-cli"
---

Running `ghost stop` stops your site from running in the background.

This command stops the site in the current folder, unless passed the name of a ghost instance or a directory. You can always discover running Ghost instances using `ghost ls`.

## Arguments

```bash
# Stop Ghost in the current folder
ghost stop

# Stop a specific Ghost instance (use ghost ls to find the name)
ghost stop [name]

# Stop the Ghost instance called ghost-local
ghost stop ghost-local
```

## Options

Run `ghost stop --help` for more detailed information.

```bash
# Stop all running Ghost instances
ghost stop --all

# Stop running the Ghost instance in a specific directory
ghost stop --dir /path/to/site/

# Tells the process manager that Ghost should not start on server reboot
ghost stop --disable
```
