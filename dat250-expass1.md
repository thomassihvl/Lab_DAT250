# DAT250 Lab 1 Report
In this lab the goal was to set up a Software Development Environment.
I had to install JAVA SDK, an IDE, Maven, Git and PostgreSQL, configure a Java Web App on Heroku and deploy it. 
In this report I'll talk about how this process went, with eventual issues, and how I validated successful steps.

## The installation process
The installation process went pretty smooth. First I checked what software I already had. I found versions of Git, Java and VSCode.
I wanted to use VSCode as IDE, as I'm very used to it and know many of the practical shortcuts and commands. However, configuring VSCode for new languages can be tricky, so I researched using it with Java. Luckily I found an installer issued by Microsoft for which included Java SDK, VSCode and Maven. I wanted a fresh install of Java anyways, so I uninstalled it and used the installer, which set up plugins in vscode for me aswell. I verified the installations by writing a small Hello World program in Java with VSCode. This worked, but didn't verify Maven. At this point I didn't undestand that the Maven I got was just a plugin. Later, when i followed the Heroku instructions, I noticed this because `mv` did not work in CMD. I followed the instructions on the [Maven homepage](https://maven.apache.org/download.cgi), downloaded a zip-file, asked around a bit how this worked, unzipped the file after putting it in a Program Files folder, then added it as a value to the PATH environment variable. It worked.

## Heroku setup process
The Heroku setup process seemed straight forward, I was just supposed to follow a guide. However, I ran into some technical issues with a PostgreSQL database. The guide told med to install PostgreSQL, which went fine with a Windows installer. I followed installation instructions and added the `/bin` folder to my PATH. I set up a Heroku account, installed Heroku with a Windows installer, cloned a Git repository with a web app and followed the instructions to deploy my first Heroku web app. I confirmed that this worked through typing `heroku open` in CMD, which pasted the web-app URL in Chrome for me, where I could visually confirm that the web app was up and running. I also read the logs with `heroku logs --tail`, confirming the web app had been visited from the server-side. 
The problems arose when I was inspecting the postgres database with `heroku pg:psql`. I could confirm that the web app was connected through a database with `heroku config` and `heroku pg`, but with `heroku pg:` I got connection issues. After trying and failing a lot, I tried connecting with my mobile Hotspot, which worked. This was weird as my friend had no problems doing this through eduroam, but I suspect this might have to do with network configs in my laptops firewall. I kept following the guide, using the instructions to both add and verify parts and configurations to the web app.
The next problem I encountered was also related to the postgres db. When trying to set up a local database I used `psql` instead of `heroku psql`. I was prompted for a password, and entered what I was quite sure was correct. I was rejected access. 100423405.5 tries later, I concluded that this cannot be a password I recently set. I did not remember at which stage in the setup process I set a password, but I remembered what I set it to, and it didn't work here. Reinstalling postgres had no effect. Instructions on how to properly reset postgres online were long and complicated, so I decided to skip this part of the tutorial for now.
After this the rest of the tutorial went smooth, I managed to host the web app locally and deploy new versions on the Heroku server through git, as well as setting config variables. 

## Summary
This lab took longer than expected. However, most of the tasks went smoothly, I just used a lot of time trying to get the database to work. I always try to troubleshoot in an organized matter, not trying the same solution twice and thinking a more while acting a little bit less. It's a fine balance, and this time I suspect I could have saved time thinking more, and trying out the same combinations of passwords less.

[Link to the web app.](https://shielded-gorge-79162.herokuapp.com/)