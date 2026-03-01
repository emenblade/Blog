---
title: "Blog Pipeline!"
date: 2026-03-01
draft: false
description: "This is how I tried to make posting on my blog as easy as social media!"
tags:
  - posts
  - docker
  - webserver
  - unraid
  - claude
  - blog
type: gallery
---

So I identified a problem with pushing posts to this website, I was really hoping to have an efficient way to add posts that I could do from my phone. Well with the power of Claude AI I was able to create a brilliantly easy pipeline for me to use. I didn't want to have to open a terminal, or wait till I got home to create a folder structure, copy the front matter, edit it, write the post and all that stuff. Then push it all to the blog. Nawh bro, no thanks! So this website is hosted on github pages. It already with the power of Hugo will automatically build the html to serve on the site each and every time there is a new commit pushed.

#### TLDR
Here is the repo to grab the blog pusher docker container, included in the repo are the necessary files to edit a blog running the mana theme to have the features included in mine. Also included is an XML template you can use in UNraid to host the docker if you'd like to do that. 

https://github.com/emenblade/blogpusher

#### Why do I want this?
Well, Its a blog, and like so many youtube tutorials on how to start bloging and all that. [Network Chuck for example](https://youtu.be/dnE7c0ELEH8?si=-dx9wLqU_cWvIuLO) They start with obsidian posts, and then the process to get the content out on the blog involves opening a terminal and pushing stuff, or running python scripts and all that. That just didn't appeal to me. I wanted to be able to blog when I was out on the go, snap some pictures, make a gallery, write down some thoughts about it, and boom its up there! I wanted to be able to blog from my phone! I didnt want to have to mess around fixing tag formatting from obsidian to how hugo processes them, I didnt like having to organize photos, put them in the right places, manually write links and all that. 
![The GUI is clean and simple!](_2-image.jpg)

#### What does this even do bro?
Well It handles all the github pushing for me, the formatting, front matter, directory construction, image file handling, it makes sure the post has a title image, and it lets you pick the order of photos in the top of post gallery. It handles all the back end git hub stuff, so making a blog post isnt any harder than a quick social media post if you want it to be.  If its going to be a longer post, like this one you can absolutely use your computer and open up your favorite note taking app, write it all out, and post it in the box. OR if you are feeling real lazy like, well I suppose you could even get your favorite AI to give you a write up and generate the post for you! On the webserver there are input boxes for the tags, title, blog body content, and then a place to input the image files. it will rename them so they present in the correct order. if you don't want a photo to show up in the gallery you can tell it that too, and it will add an underscore to the front of the file name, which the gallery ignores. If you forget how to use markdown or want to link an image in line there is a cheat sheet at the bottom! 
![mange posts](_3-image.jpg)
![handles directory and renames photos](_4-image.jpg)
![includes a cheat sheet in case you forget markdown](_6-image.jpg)
#### Cool story bro, how do I start?
Well, so you're gonna need to install some things first.  
- [Hugo](https://gohugo.io) 
- [Mana theme](https://github.com/Livour/hugo-mana-theme) 
So if you're making a lil bloggy blog, and aren't expecting a tonne of traffic, I'd recommend using [github pages](https://docs.github.com/en/pages). 
If you do, then you can github rebuild your site, every time you push by using a [Workflow](https://gohugo.io/host-and-deploy/host-on-github-pages/).
Once you have all that working, well thats where this custom brewed piece of tech made by my lil buddy Claude comes into play. See cause right now, if you want to add a post, you have to make directories, and files and push things and its not super hard, you made it this far, BUT its not simple like it should be. THE youtubers sold you on a dream and let me tell ya, while their python scripts and stuff do work, its just not 2026 levels of easy enough for this guy! 

#### My secret sauce! 
So as anticipated, of course I've got a home lab. I personally have a little box in the closet running unraid. I love the lil thing, deploying containers could not be easier, its been rock solid reliable all that yada yada. So if you have something that can run some python scripts, and could host a little webserver on your home network here's how you make things super stupid simple for ya! 

- Install [BlogPusher](https://github.com/emenblade/blogpusher)
  - If you're running Unraid or can setup dockers using an  [XML file](https://github.com/emenblade/blogpusher/blob/main/unraid-template.xml) scroll down to Unraid section for some special sauce for that. 

- Use the setup page, it will push some additional features to your site, I.E. the gallery stuff. 
- You can delete or view posts using the manage posts section, 
- You can Push new posts, including pictures, they will be renamed to appear in the right order 
- Everything gets put into the right places and pushed where it needs to go. Couldn't be simpler! Once the push is committed, git hub rebuilds your page, it takes about a minute or 2 and then bingo bango you're live. 
- The webserver is mobile friendly, so If you have some kinda vpn, to your home lab network, you can be blogging with about as much effort as making a social media post. You're friggen welcome! 


#### Unraid
Okay so if you're running Unraid, you're gonna wanna add the  [XML file](https://github.com/emenblade/blogpusher/blob/main/unraid-template.xml) to a directory on your flash drive. "/config/plugins/dockerMan/templates-user/" 
So you *could* unplug the drive, put the file there and then put it back in your NAS. ORRR you could install a plugin for unraid called [Dyanmix File Manager](https://github.com/unraid/dynamix) Which if I'm reading the docs on the repo right, I guess on newer installs of unraid it might just come preinstalled?? Any way using that you can add the [XML file](https://github.com/emenblade/blogpusher/blob/main/unraid-template.xml) to the templates folder and from there you can add it as a new container. If you have more than one blog, when youre deploying the webservers, just give them different names and ports. ![This is where you throw the xml!](_5-image.jpg)

Any way for a Blog more about making stuff work than the actual content I reckon this was more than enough of a write up! Happy blogging! 
-Alex <3