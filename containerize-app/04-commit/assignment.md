---
slug: commit
id: l6d7bdfdpvev
type: challenge
title: Committing the new container image
tabs:
- id: jrexjydtpocg
  title: Terminal
  type: terminal
  hostname: rhel
  cmd: tmux attach-session -t "rhel-session" > /dev/null 2>&1
difficulty: basic
timelimit: 1
enhanced_loading: null
---
At this point, the container is configured.  It is time to transition from a
working container into a committed image.  In the command below, you will use
the `buildah` command to commit the working container to an image called:
`moon-buggy`.

```bash,run
buildah commit ubi-working-container moon-buggy
```

<pre class="file">
Getting image source signatures
Copying blob 226bfaae015f skipped: already exists
Copying blob 70056249a0e2 skipped: already exists
Copying blob b03eece6d0e2 done
Copying config dbb1368db3 done
Writing manifest to image destination
Storing signatures
dbb1368db3f9b5f5cd651581e3c6e0bee242c25ef8ec68d2bef9f18e98f05209
</pre>

The above output shows that the commit was successful, however you can verify
this by looking at the available container images on the system.

```bash,run
podman image list
```

<pre class="file">
REPOSITORY                            TAG      IMAGE ID       CREATED          SIZE
localhost/moon-buggy                  latest   dbb1368db3f9   15 seconds ago   335 MB
registry.access.redhat.com/ubi9/ubi   latest   a1f8c9699786   4 weeks ago      211 MB
</pre>

Notice in the output above that `moon-buggy` is the first container image
listed in the `podman image list` output.
