---
slug: prepare-for-conversion
id: gpz685jv20qj
type: challenge
title: Prepare for conversion
tabs:
- title: centos
  type: terminal
  hostname: host
  cmd: ssh -o "StrictHostKeyChecking no" root@centos
difficulty: basic
---


Before you begin the installation process, verify that you are running CentOS Linux and on the latest minor version.

```bash
cat /etc/centos-release

```

<pre class='file'>
# cat /etc/centos-release
CentOS Linux release 7.9.2009 (Core)
</pre>

## Enabling the Convert2RHEL repository

The Convert2RHEL RPM is an offical Red Hat package. Therefore it is readily availble from the Red Hat software repository (CDN). As your CentOS server is not subscribed to the Red Hat CDN, you will need to enable the Convert2RHEL repository.

First, you will pull down the GPG signing key:

```bash
curl -o /etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release https://www.redhat.com/security/data/fd431d51.txt

```

<pre class='file'>
# curl -o /etc/pki/rpm-gpg/RPM-GPG-KEY-redhat-release https://www.redhat.com/security/data/fd431d51.txt
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1855  100  1855    0     0   2324      0 --:--:-- --:--:-- --:--:--  2324
</pre>

Second, download the SSL certificate:

```bash
curl --create-dirs -o /etc/rhsm/ca/redhat-uep.pem https://ftp.redhat.com/redhat/convert2rhel/redhat-uep.pem

```

<pre class='file'>
# curl --create-dirs -o /etc/rhsm/ca/redhat-uep.pem https://ftp.redhat.com/redhat/convert2rhel/redhat-uep.pem
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  7411  100  7411    0     0  15260      0 --:--:-- --:--:-- --:--:-- 15280
</pre>

Thirdly, download the convert2rhel repository file:

```bash
curl -o /etc/yum.repos.d/convert2rhel.repo https://ftp.redhat.com/redhat/convert2rhel/7/convert2rhel.repo

```

<pre class='file'>
# curl -o /etc/yum.repos.d/convert2rhel.repo https://ftp.redhat.com/redhat/convert2rhel/7/convert2rhel.repo
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   247  100   247    0     0    509      0 --:--:-- --:--:-- --:--:--   510
</pre>

Now we'll update the centos host and reboot it. The convert2rhel utility requires an up-to-date centos host.

Enter the following command.

```bash
yum update -y && reboot
```

The terminal will lose connection with the centos host leaving the message `exited`.

![exited](../assets/exited.png)

You can reconnect the session in the `centos` tab if desired. Refresh the `centos` tab until you are reconnected.

![refresh](../assets/refreshbutton.png)

Proceed to the next step where the terminal will automatically reconnect to the centos host.
