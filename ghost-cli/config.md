---
title: "config"
date: "2018-10-01"
meta_title: "Ghost-CLI commands: config - Documentation"
meta_description: "Create and manage configuration for a Ghost instance using advanced CLI tooling."
next:
  url: "/api/ghost-cli/install/"
  title: "Install"
keywords:
    - cli
    - ghost
    - install
    - config
sidebar: "ghost-cli"
---

Create and manage configuration files for a Ghost instance

Configuring your Ghost publication can be done efficiently using the `ghost-cli` tool, which is the most popular way to install an instance of Ghost. 

> You can also edit your config manually - check out the [config guide](/concepts/config/) to find out more. 


## Arguments

`ghost config` accepts two optional arguments: `key` and `value`. Here are the three different combinations and what happens on each of them:

```bash 
# Create a new config file for the particular env
ghost config

# Find and return the value in the config for the key passed
ghost config [key] 

# Set a key and a value in the config file
ghost config [key] [value]

# Set the url for your site
ghost config url https://mysite.com
```

The `ghost config` command only affects the configuration files. In order for your new config to be used, run `ghost restart`.


## Options

If you're using `ghost config` to generate a configuration file, you can supply multiple key-value pairs in the form of options to avoid being prompted for that value.

All of these options can also be passed to `ghost install` and `ghost setup` , as these commands call `ghost config`.

See the [config guide](/concepts/config/) or run `ghost config --help` for more detailed information.

```bash:title=Ghost Options:
# URL of the site including protocol
--url https://mysite.com

# Admin URL of the site
--admin-url https://admin.mysite.com

# Port that Ghost should listen on 
--port 2368

# IP to listen on 
--ip 127.0.0.1

# Transport to send log output to
--log ["file","stdout"]
```

<br />


```bash:title=Database Options:
# Type of database to use (sqlite3 or mysql)
--db

# For sqlite3 we just need a file:
# Path to database file
--dbpath content/data/ghost_dev.db

# For mysql we need full credentials:
# Database host 
--dbhost localhost

# Database user name
--dbuser ghost

# Database password
--dbpass ****

# Database name
--dbname ghost_dev
```

<br />

```bash:title=Mail Options:
# Mail transport, E.g SMTP, Sendmail or Direct
--mail SMTP

# Mail service (used with SMTP transport), E.g. Mailgun, Sendgrid, Gmail, SES...
--mailservice Mailgun

# Mail auth user (used with SMTP transport)    
--mailuser postmaster@something.mailgun.org

# Mail auth pass (used with SMTP transport)
--mailpass ****

# Mail host (used with SMTP transport)
--mailhost smtp.eu.mailgun.org

# Mail port (used with SMTP transport)
--mailport 465
```

<br />


```bash:title=Service Options:
# Process manager to run with (local, systemd)
--process local
```

## Debugging

In order for your new config to be used, run `ghost restart`.
