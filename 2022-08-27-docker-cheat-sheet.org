#+title: Docker Cheat Sheet
#+subtitle: Some docker commands that I often use
#+description: This is a set of docker commands that comes handy very often
#+date: 2022-08-27
#+keywords: Docker, linux
#+html_link_home: ./
#+html_link_up: ./
#+SETUPFILE: org-templates/level-0.org

* To get shell access in a running container
#+BEGIN_SRC bash
docker exec -it <container> bash
#+END_SRC
The above starts a bash process in the running container, interactively.
If ~bash~ is not available in the container, ~sh~ can be used.
* Using docker to do something in the local machine, like compiling node applications
#+BEGIN_SRC bash
docker run -it -v$(pwd):/workdir -w /workdir <image> <command>
#+END_SRC
The above command creates a docker container using the specified ~image~.
It mounts the present working directory as ~/workdir~, set the same as docker's working directory.
And the command is executed inside the container.

For example, to run ~npm install~ in a node project called ~test-pjt~ without installing node in the machine
#+BEGIN_SRC bash
docker run -it -v$(pwd):/workdir -w /workdir/test-pjt node:16.17.0-alpine3.16 npm install
#+END_SRC

* Oneliner to delete all docker containers from the machine
#+BEGIN_SRC bash
docker ps -a | cut -f 1 -d ' ' | tail -n +2 | xargs docker rm
#+END_SRC
Removes all docker containers from the local machine
