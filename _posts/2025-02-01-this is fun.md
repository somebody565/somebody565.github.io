---
title: This is fun!
author: Corentin
date: 2025-02-01 23:32:00 -500
categories: [homelab,hardware]
tags: [servers,dell,hp,supermicro]
---

# Welcome

Hello and welcome to my blog! Lets start this journey together!

## Install Docker

To install docker, see 

## Install Rancher

The two paths in the workload configuration need to be reversed:

- `Path on the Node` should be `mc`
- `Mount Point` should be `/data`

You'll want to use a command similar to this so that there aren't any port conflicts with other services or kubernetes itself.

Also, you may want to consider pinning your docker tag to a version other than `latest` to make backing up and upgrading easier. See [here](https://github.com/rancher/rancher/tags) for the latest version.

```bash
docker run -d --restart=unless-stopped -p 9090:80 -p 9091:443 --privileged -v /opt/rancher:/var/lib/rancher --name=rancher_docker_server rancher/rancher:latest
```

## Troubleshooting

- Make sure you have a static IP on your Rancher host
- Be sure to use the ports above if you want to add SSL later and use commands in future videos
- The new UI is now the "Cluster Explorer".You can toggle between this and the "Cluser Manager" UI by clicking the button.
- Do not create workloads in the `local` cluster.This is a management cluster for Rancher.You should create new cluster for your workload, just like in this video.

## Links

🛍️ Check out the new Merch Shop at <https://l.technotim.live/shop>

⚙️ See all the hardware I recommend at <https://l.technotim.live/gear>

🚀 Don't forget to check out the [🚀Launchpad repo](https://l.technotim.live/quick-start) with all of the quick start source files