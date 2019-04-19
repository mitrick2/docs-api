---
title: "start"
date: "2018-10-01"
meta_title: "Ghost-CLI commands: start - Documentation"
meta_description: "Run Ghost in the background using your default process manager with a single command using Ghost-CLI. Read more in the official documentation." 
next:
  url: "/api/ghost-cli/stop/"
  title: "Stop"
keywords:
    - cli
    - ghost
    - start
    - install
sidebar: "ghost-cli"
---

Running `ghost start` will start your site in background using the configured process manager.

The default process manager is systemd, or local for local installs. 

The command must be executed in the directory where the Ghost instance you are trying to start lives, or passed the correct directory using the `--dir` option.


## Options

The `ghost start` command always runs `ghost doctor` first to check that your site will run correctly.

Run `ghost start --help` for more detailed information.

```bash
# Start running the Ghost instance in a specific directory
ghost start --dir /path/to/site/

# Start ghost in development mode
ghost start -D, ghost start --development

# Tells the process manager to restart Ghost on server reboot
ghost start --enable

# Tells the process manager not to restart Ghost on server reboot
ghost start --no-enable

# Disable memory availability checks in ghost doctor 
ghost start --no-check-mem
```

## Debugging

If running `ghost start` gives an error, try using `ghost run` to debug the error.
