---
slug: getting-started
id: xoq0aopvftwp
type: challenge
title: Install MySQL
notes:
- type: text
  contents: |
    # Goal: Set up a database using MySQL

    # Overview

    After completing this scenario, users will be able to configure a MySQL server and set up a web interface for it.

    ## Concepts included in this scenario:

     * SQL
     * Relational database design
     * Database security fundamentals
tabs:
- id: bpjzbkjh4ryd
  title: Terminal
  type: terminal
  hostname: rhel
  cmd: tmux attach-session -t "rhel-session" > /dev/null 2>&1
- id: fv8nkjgw5eys
  title: RHEL Web Console
  type: website
  url: https://rhel.${_SANDBOX_ID}.instruqt.io:9090
  new_window: true
difficulty: basic
timelimit: 6000
enhanced_loading: null
---
First, install MySQL by running the following command:
```bash,run
dnf install -y mysql-server
```

Next, start MySQL with this command:
```bash,run
systemctl start mysqld.service
```

Finally, use `systemctl` to allow MySQL to automatically start when the system boots:
```bash,run
systemctl enable mysqld.service
```