---
slug: configure-a-web-interface
id: hf89dvztwoa0
type: challenge
title: Configure a Web Interface
notes:
- type: text
  contents: Next, you will set up a web interface that will allow you to interact
    with your database through a graphical user interface
tabs:
- id: s4sa7dvfbhgt
  title: Terminal
  type: terminal
  hostname: rhel
  cmd: tmux attach-session -t "rhel-session" > /dev/null 2>&1
- id: 7x7yk7huthdg
  title: RHEL Web Console
  type: website
  url: https://rhel.${_SANDBOX_ID}.instruqt.io:9090
  new_window: true
- id: dvqtljlxer5z
  title: Adminer
  type: website
  url: http://rhel.${_SANDBOX_ID}.instruqt.io/adminer
  new_window: true
difficulty: basic
timelimit: 600
enhanced_loading: null
---
SQL servers are easiest to manage through the terminal, but when you are first getting started, sometimes a GUI can make things less intimidating. In your own SQL server, you can choose to skip the configuration of a GUI, but we'll set up the GUI in our lab.

We will use Adminer, but you can also use tools like phpMyAdmin and MySQL Workstation.

To install Adminer, run the following command to install php and the php MySQL extension. These are required to successfully run Adminer.
```bash,run
dnf install -y php php-mysqli
```

Next, run the following command to make a directory for Adminer and use it as your working directory:
```bash,run
mkdir /var/www/html/adminer && cd /var/www/html/adminer
```

To download Adminer from its GitHub repository into the directory you made, run this command:
```bash,run
wget -O index.php https://github.com/vrana/adminer/releases/download/v4.8.1/adminer-4.8.1-en.php
```

Next, configure Adminer's ownership and permissions:
```bash,run
chown -R apache:apache index.php /var/www/html/adminer/
chmod -R 775 /var/www/html/adminer/
```

To complete the installation, restart the web server through `systemctl restart`:
```bash,run
systemctl restart httpd
```

Now, go ahead and select the `Adminer` tab at the top of your Instruqt window.

Log in with the following settings:
* System: `MySQL`
* Server: `localhost`
* Username: `root`
* Password: `rhel`
* Database: `MyDatabase`

You will now see the tables you created earlier:
![](../assets/Adminer_MyDatabase.png)
