---
title: "log"
date: "2018-10-01"
meta_title: "Ghost-CLI utilities: log - Documentation"
meta_description: "Start a Ghost instance in the foreground for debugging"
next:
  url: "/api/ghost-cli/knowledgebase/"
  title: "Advanced"
keywords:
    - cli
    - ghost
    - run
    - debugging
sidebar: "ghost-cli"
---

View the access and error logs from your Ghost site (not the CLI).

By default `ghost log` outputs the last 20 lines from the access log file for the site in the current folder. 

### Log Behaviour

Ghost's default log config creates log files in the `content/logs` directory, and creates two different files:

1. An **access log** that contains all log levels, named e.g. `[site_descriptor].log` 
2. An **error log** that contains error-level logs _only_, named e.g. `[site_descriptor].error.log` 

The site descriptor follows the pattern `[proto]__[url]__[env]` e.g. `http__localhost_2368__development` or `https__mysite_com__production`. The files are be rotated, therefore you may see many numbered files in the `content/logs` directory.


## Arguments

```bash
# View last 20 lines of access logs
ghost log

# View logs for a specific Ghost instance (use ghost ls to find the name)
ghost log [name]

# View logs for the Ghost instance called ghost-local
ghost log ghost-local
```

## Options

Run `ghost log --help` for more detailed information.

```bash
# Show 100 log lines
ghost log -n 100, ghost log --number 100

# Show only the error logs
ghost log -e, ghost log --error

# Show 50 lines of the error log
ghost log -n 50 -e

# Follow the logs (e.g like tail -f)
ghost log -f, ghost log --follow

# Follow the error log
ghost log -fe

# Show logs for the Ghost instance in a specific directory
ghost log --dir /path/to/site/

```

## Debugging 

There may be some output from Ghost that doesn't appear in the log files, so for debugging purposes you may also want to try the [ghost run](/api/ghost-cli/run) command.

If you have a custom log configuration the `ghost log` command may not work for you. In particular the `ghost log` command requires that file logging is enabled. See the [logging configuration docs](/concepts/config/#logging) for more information. 
