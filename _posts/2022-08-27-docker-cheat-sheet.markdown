---
layout: post
title: Docker Cheat Sheet
date: 2022-08-27
categories: cheat-sheets
---

## To get shell access in a running container
{% highlight shell %}
docker exec -it <container> bash
{% endhighlight %}
The above starts a bash process in the running container, interactively.
If `bash` is not available in the container, `sh` can be used.

## Using docker to do something in the local machine, like compiling node applications
{% highlight shell %}
docker run -it -v$(pwd):/workdir -w /workdir <image> <command>
{% endhighlight %}

The above command creates a docker container using the specified `image`.
It mounts the present working directory as `/workdir`, set the same as docker's working directory.
And the command is executed inside the container.

For example, to run `npm install` in a node project called `test-pjt` without installing node in the machine
{% highlight shell %}
docker run -it -v$(pwd):/workdir -w /workdir/test-pjt node:16.17.0-alpine3.16 npm install
{% endhighlight %}

## Oneliner to delete all docker containers from the machine
{% highlight shell %}
docker ps -a | cut -f 1 -d ' ' | tail -n +2 | xargs docker rm
{% endhighlight %}
Removes all docker containers from the local machine
