---
title: "restart"
date: "2018-10-01"
meta_title: "Ghost-CLI commands: restart - Documentation"
meta_description: "Stop and start your Ghost site with this simple command with the Ghost-CLI. Read more in the Ghost documentation."
next:
  url: "/api/ghost-cli/update/"
  title: "Update"
keywords:
    - cli
    - ghost
    - stop
    - install
sidebar: "ghost-cli"
---

Running `ghost restart` will stop and then start your site using the configured process manager.

The default process manager is systemd, or local for local installs. 

The command must be executed in the directory where the Ghost instance you are trying to start lives, or passed the correct directory using the `--dir` option.

## Options

Run `ghost restart --help` for more detailed information.

```bash
# Start running the Ghost instance in a specific directory
ghost restart --dir /path/to/site/

```

## Debugging

If running `ghost restart` gives an error, try using `ghost run` to debug the error.
