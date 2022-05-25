+++
weight = 50
title = "File access limits"
draft = true
+++

To reduce the impact of malicious scripts, rbxmk limits a script's access to the
file system. An environment specifies a number of **root** directories. Only
file paths within a root can be accessed. A root path itself cannot be accessed,
except for moving files into ([fs.rename][fs.rename]), or getting the contents
of ([fs.dir][fs.dir]).

The following directories are marked as roots:
- The working directory (<code>[path.expand][path.expand]("$wd")</code>).
- The directory of the first running script file (<code>[path.expand][path.expand]("$rsd")</code>).
- The temporary directory provided by rbxmk (<code>[path.expand][path.expand]("$tmp")</code>).
