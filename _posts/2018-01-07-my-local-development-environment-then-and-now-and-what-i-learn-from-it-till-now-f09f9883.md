---
ID: 31
post_title: 'My Local Development Environment&#8230;. then and now&#8230; and What I learn from it till now. 😃'
author: rahul
post_excerpt: ""
layout: post
permalink: 'https://rahulprajapati.me/my-local-development-environment-then-and-now-and-what-i-learn-from-it-till-now-%f0%9f%98%83/'
published: true
post_date: 2018-01-07 14:17:26
---
My requirement for local environment is to be set up a WordPress/Php sites so I needed PHP, MySQL, Apache/Nginx services. 👷🏻‍♂️

Ok. In one line I'm using my <a href="https://github.com/rahulsprajapati/wp-local-docker">own setup</a> with docker-compose, customized the <a href="https://github.com/10up/wp-local-docker/">10up's wp-local-docker</a> environment with support of multiple sites setup.

I was using <a href="http://easyengine.io/">easyengine</a>  on my ubuntu system and it was easy to setup with few commands only.

But I kinda always messing around with my machine and endup being formatting my system 😂 sometimes just because I wanted to try diff OS so in all of this times I've to backup my all the sites data from my user to diff dir and had to dump all the databases and again setup everything and put all the things back to gather.  Always make me sick.

In meantime, I heard about the <a href="https://github.com/Varying-Vagrant-Vagrants/VVV">VVV</a>/Vagrant and tried that but never liked that just because of the performance and my machine get too slow, and I'm using chrome 😛 so nahh... never went with that. But yeah on few projects I had to use this because of the requirements of the same system environment.

Ok and then I heard about Docker<img class="alignnone wp-image-47" src="https://rahulprajapati.me/wp-content/uploads/2018/01/apple-icon-76x76-e1515322056519.png" alt="" width="26" height="26" /> and try to use that and seem like this is what I wanted for long. ( I took some help from my friends who are good with server-side things and learn what it is. ) I can say its a standalone environment ( kinda like VVV but better ) now I can able to setup everything wherever I want with all shared required directory of easyengine. I build my <a href="https://hub.docker.com/r/rahulprajapati/ee-ubuntu/">first image</a> with easyengine setup and then I was using the share volumes and used it for a while. In doing so I got to know more about the Nginx, MySQL configurations where I needed the files to be located.
<blockquote>docker run -it --name=ee -p 80:80 -p 22222:22222 -p 3306:3306 -p 443:443 -v ./www:/var/www -v ./lib/mysql:/var/lib/mysql -v ./lib/ee:/var/lib/ee -v ./etc/nginx:/etc/nginx -v ./etc/hosts:/etc/hosts -v ./etc/ee:/etc/ee rahulprajapati/ee-ubuntu</blockquote>
So, at first I started with this and this solves my problem now when I format my machine or change my system all I need is this dir, setup docker and run the command, And I got all my sites with the same data. I don't need to backup any sql dump and reimport it, or take a backup of my sites I can just keep my working dir where ever I want.

And this helps me when I moved from Linux <img class="alignnone size-full wp-image-54" src="https://rahulprajapati.me/wp-content/uploads/2018/01/icons8-linux-26.png" alt="" width="26" height="26" /> to Mac <img class="alignnone size-full wp-image-65" src="https://rahulprajapati.me/wp-content/uploads/2018/01/icons8-apple-26.png" alt="" width="26" height="26" /> I just needed my local environment dir where I put all the things. That's how I went into Docker.

But that wasn't it, it never will be 😂 we got docker-composer and learn about it also learn that we should use the different container for each service which is good for performance and we can share services between other containers/services.

Then I tried some of the opensource development environment of WordPress environments and see what and how they are using it. I came up with this two environment setups.
<ul>
 	<li><a href="https://github.com/joshbetz/docker-wp">https://github.com/joshbetz/docker-wp</a></li>
 	<li><a href="https://github.com/10up/wp-local-docker">https://github.com/10up/wp-local-docker</a></li>
</ul>
And I liked to go with the second one, 10up's wp-local-docker and used it for a while. Because of following reasons ( this might be silly reasons but was checking my requirements ).
<ol>
 	<li>I can able to access WordPress root dir easily.</li>
 	<li>Easily run the commands in containers using docker-composer. Helps in wp cli commands mostly.</li>
 	<li>It has mailcatcher, memcached, elasticsearch services.</li>
</ol>
<span style="font-size: 1rem;">Now, this setup is for the </span>single site<span style="font-size: 1rem;"> so I always have to </span>setup<span style="font-size: 1rem;"> this for each new projects and then I missed easyengine. And now I thought that I can make it happen just needed to do some tweaks and tricks in my setup. So,  I went around for <a href="http://nginx.org/en/docs/http/request_processing.html">Nginx config file requirements</a> and how to handle multiple site domains with diff sites.</span>

And finally got it working fine, now I'm using my own customised docker-compose setup on my Mac.

&nbsp;

<a href="https://github.com/rahulsprajapati/wp-local-docker">https://github.com/rahulsprajapati/wp-local-docker</a>