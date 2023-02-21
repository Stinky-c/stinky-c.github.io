+++
title = "Homelab"
date = "2022-11-25T17:53:48-08:00"
author = "Bucky"
authorTwitter = "stinky_c" #do not include @
tags = ["Homelab", "WIP"]
keywords = ["Homelab", ""]
description = "My intro to homelabbing"
showFullContent = false
readingTime = true
hideComments = true
+++

# My Intro to Homelabbing

A first note: I am only a beginner with time to burn, desire to learn.
So recently I bought another [SSD](https://www.crucial.com/ssd/mx500/ct1000mx500ssd1) for my original server. After installing I migrated my data to the new drive and removed and kept the old drive. While the hardware isn't very much nor powerful it does provide enough space for me to experiment and tinker.

## My hardware

- Raspberry pi 4 - 8gb
    - bought well over a year ago and started my self hosting adventure
- Recycled hardware
    - CPU: [i7-4790](https://www.intel.com/content/www/us/en/products/sku/80806/)
        - 4 cores
        - 8 threads
        - Base 3.6 GHz
        - Turbo 4.0 GHz
    - Storage: [Crucial mx500 1tb](https://www.crucial.com/ssd/mx500/ct1000mx500ssd1)
        - I had bought one a year before for my personal workstation, and it has been working well
    - RAM: 24gb
        - It is an odd amount, but it is running well
        - Random sticks that match
        - 2x4gb
        - 2x8gb
        - DDR3 @ 1333MHz

Post install I went right to work getting things running. Previously I had been running some game servers on the Recycled Server and PiHole on the rpi4, but now my tech has expanded out from that.

## My Old Stack

- RPI4
    - [Yacht](https://yacht.sh/)
        - [GH]
        - I had found it to be unreliable
    - [A Self Written Discord Bot](https://github.com/Stinky-c/DisBot)
        - It has become really old, but provides useful tools
    - [PiHole](https://pi-hole.net/)
        - [GH](https://github.com/pi-hole/pi-hole)
        - A DNS sinkhole
        - I am still running the default lists
- Recycled
    - Various game servers
    - Docker containers
    - A linux 64-bit build server

After I finished the install and upgrade I migrated my stack.

## My New Stack

- Recycled
    - [Portainer CE](https://www.portainer.io/)
        - [GH](https://github.com/portainer/portainer)
    - [Traefik Proxy](https://traefik.io/traefik/)
        - [GH](https://github.com/traefik/traefik)
    - [Uptime Kuma](https://github.com/louislam/uptime-kuma)
    - [Dashy](https://dashy.to/)
        - [GH](https://github.com/Lissy93/dashy)
    - [Watchtower](https://containrrr.dev/watchtower/)
        - [GH](https://github.com/containrrr/watchtower/)
- RPI4
    - [PiHole](https://pi-hole.net/)
        - [GH](https://github.com/pi-hole/pi-hole)
    - Portainer Agent
    - [A Self Written Discord Bot](https://github.com/Stinky-c/DatBot)
        - ~~A rewrite should be soon to come~~
        - As of roughly 23/2/11 I had deployed the newly update bot, and update the URL on this page

## My Thoughts on the Tech

I may have missed some important stuff, but I ignored my disabled services like game panels.

Portainer is a a docker and kubernetes management UI. A similar solution is rancher but I'm yet to try it. So far my experience with portainer has been nice, it provides a useful UI that I find simple to use while providing all of the needed features. The default templates aren't the best for selfhosting, I checked out some resources and have found [`xneo1/portainer_templates`](https://raw.githubusercontent.com/xneo1/portainer_templates/master/Template/template.json) sufficient enough.

Traefik is a reverse proxy and load balancer configured using docker labels, command line arguments or yaml files. I had thought of trying [Nginx Proxy Manager](https://nginxproxymanager.com/) but I went with traefik. It provides the reliability I depend on, while being complex enough to make intricate networks. It can be difficult to configure but is well worth the time spent.

Dashy is a dashboard. Plain and simple. It does however provide different widgets compared to other dashboards I've seen and used. It provides widgets powered by glances, and an embedded HTML widget. A list of widgets can be found [here](https://dashy.to/docs/widgets/). Some alternatives to it are [`benphelps/homepage`](https://github.com/benphelps/homepage), and [`bastienwirtz/homer`](https://github.com/bastienwirtz/homer).
