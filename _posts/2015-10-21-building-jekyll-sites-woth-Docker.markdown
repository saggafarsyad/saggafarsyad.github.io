---
layout: post
title:  "Building Jekyll Sites with Docker"
date:   2015-10-21 21:47:00
categories: jekyll windows mac blog lang-english docker
---
Jekyll is a static site generator. You write your post in a markdown file and Jekyll will render it beautifully. So you don't waste your time to format or design it. No database required make it light, fast and secure. Another great thing is you can have you own free blog  with github.io domain! Cool, right?

To build a Jekyll sites locally, you'll need a Linux macihine. My machine is Windows 10 and Jekyll is not officially supported on Windows platform. Another alternative to build Jekyll site is using Docker. You can download Docker Toolbox [here][docker-toolbox]. After installing Docker Toolbox, run **Docker Quickstart Terminal**.

Jekyll has official [Docker images][jekyll-docker], but I didn't find any good tutorial on the web. Here is what I've done:

### 1. Create a local folder
	mkdir <YOUR_SITE>
	cd <YOUR_SITE>

### 2. Run *bash* from official Jekyll Docker Images

Some tutorial out there use Jekyll Docker image with *latest* or *stable* tag, I found out using *builder* tag is better because it has **bash**, so you'll write less command. Call this line on Docker terminal:

    docker run --rm -i -t --name=jekyll-builder --volume=/$(pwd):/srv/jekyll/ -p 4000:4000 jekyll/jekyll:builder bash

### 3. Create a new site 

    jekyll new .

### 4. Edit your site  
You can start by editin`g the **_config.yml** file. For more, go to the [Jekyll Documentation][jekyll-docs].

### 5. Build and Preview the site

To build or generate the site, call  
`jekyll build`.

To preview site, go to your browser and go to `<DOCKER_MACHINE_IP>:4000`. For example, mine is `192.168.99.100:4000`. If you don't know the IP, open a new **Docker Quickstart Terminal** and call  

    docker-machine env default

Always remember that Jekyll is a static site generator. It means every time you make changes in the site, you must build it by calling `jekyll build`. But don't worry, you can also call:

    jekyll serve --watch --force_polling

Jekyll will automatically build the site everytime you make changes such as adding a new post or editing templates. 

**Notes for Mac users**   
- On step 2, remove the slash in `/$(pwd)`  
- When calling `jekyll serve`, remove `--force_polling` argument

[docker-toolbox]: https://www.docker.com/docker-toolbox
[jekyll-docker]: https://github.com/jekyll/docker
[jekyll-docs]: http://jekyllrb.com/docs/home/
