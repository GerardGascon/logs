---
layout: log
title: "Exposed my home server"
subtitle: "I wasn't able to port forward for some reason"
version: 0.1
toc: false
---

For those who don't know, I have a Raspberry Pi 5 at home. At first, I used it as a basic home server just for personal
use, but recently I've started sharing it. The problem was that I couldn't get port forwarding to work, but as a
workaround I started using [Cloudflared](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/)
as it made things really simple.

Some time after that, while I was hosting my Forgejo Git server, I found that I couldn't make a 100MB push due to a
limitation on Cloudflared.

After some time digging, I discovered [Tailscale](https://tailscale.com/), which somewhat worked.

## The challenge: Make it public

The main reason for me to use Cloudflared was for me to be able to access my hosted services when I was away from home.
This problem was solved with Tailscale, the problem is that there were some other services that I also wanted to expose
for anybody on the internet, and that was just not possible by using Tailscale alone.

### NGINX

Luckily, there are these things called Reverse Proxies that can reroute a request to another service very easily. I
specifically use [nginx](https://nginx.org/) in my projects, and for this I used it too.

Let's say I have a url [git.gerardgascon.com](https://git.gerardgascon.com/) that points to a
cheap VPS hosted on whatever place you want (I use a $4 Droplet on [DigitalOcean](https://digitalocean.com)). Inside
that server there are two Docker containers running, one has Tailscale in it, and the other has nginx and exposes ports
80 and 443 (HTTP and HTTPS).

For each url I have, nginx takes it and routes it through the specific IP and port of my home server connected to my
Tailnet.

---

Anyway, this is a really basic setup, but it just works fine. If you are curious, you can check the Docker and nginx
configurations over [here](https://git.gerardgascon.com/Geri/reverse-proxy-setup/) (A link proudly hosted on my home
server).