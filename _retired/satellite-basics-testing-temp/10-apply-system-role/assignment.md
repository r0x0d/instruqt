---
slug: apply-system-role
id: iaq6efi6s46q
type: challenge
title: Apply System Role
teaser: Apply System Role to hosts
notes:
- type: text
  contents: RHEL System Roles is a collection of Ansible roles and modules that provide
    a stable and consistent configuration interface to automate and manage multiple
    releases of Red Hat Enterprise Linux.
tabs:
- title: Satellite Server
  type: terminal
  hostname: satellite
- title: Satellite Web UI
  type: external
  url: https://satellite.${_SANDBOX_ID}.instruqt.io
- title: rhel1
  type: terminal
  hostname: rhel1
- title: rhel1 Web Console
  type: external
  url: https://rhel1.${_SANDBOX_ID}.instruqt.io:9090
- title: rhel2
  type: terminal
  hostname: rhel2
- title: rhel2 Web Console
  type: external
  url: https://rhel2.${_SANDBOX_ID}.instruqt.io:9090
difficulty: basic
timelimit: 1
---
<!-- markdownlint-disable MD033 -->

_**NOTE:**_ Before starting this challenge, make sure that your hosts have finished rebooting from the previous challenge. You can easily check by clicking on the terminal tab to check that you have a working session with each host. ![tabs](../assets/hosttab.png)

Earlier, we configured the our host group to have a system role applied to it. Specifically, port 80/tcp was to be opened. You can find out more about [RHEL System Roles here](https://access.redhat.com/articles/3050101).

Once again, navigate to `All Hosts`.

![all hosts](../assets/allhostssystemrole.png)

Next we'll do the following.

1) Select both hosts.
2) Click `Select Action`.
3) Select `Run all Ansible roles`.

![apply system roles](../assets/applysystemroles.png)

In the `Overview` menu you'll be shown the status of the jobs.

![system role](../assets/systemrolestatus.png)

If you want, click on a host to view the application of the system role.

![firewall stpes](../assets/firewallsteps.png)

You can verify that port 80/tcp has been opened by doing the following.

Click on the terminal tab for `rhel1` **or** `rhel2`.

![host tab](../assets/hosttab.png)

Copy and paste the following into the cli.

```bash
firewall-cmd --list-all
```

![fwcmd](../assets/firewallcmdoutput.png)
