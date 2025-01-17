---
slug: install-jupyter
id: cgzzqtsyz14z
type: challenge
title: Install Jupyter Lab
notes:
- type: text
  contents: In this step, you will install packages into your Conda environment to
    host the Jupyter Notebook.
tabs:
- id: rgjm7vewflna
  title: Terminal
  type: terminal
  hostname: rhel
  cmd: tmux attach-session -t "rhel-session" > /dev/null 2>&1
difficulty: basic
timelimit: 600
enhanced_loading: null
---
First, activate your virtual environment by running the following command:
```bash,run
conda activate jupyter
```
Once you have activated the virtual environment, the command line should look like this:
<pre class="file">
(jupyter) <span style="color:green;">root@rhel</span>:~#
</pre>
Run the following command to install Jupyter Lab:
```bash,run
pip install jupyter
```
Next, install Matplotlib, Numpy, and Pandas:
```bash,run
pip install matplotlib numpy pandas
```
Jupyter Lab will host your Jupyter Notebooks, Matplotlib is for output visualization, and both Pandas and Numpy are for data analysis. continue to the next step to run a Jupyter Notebook.