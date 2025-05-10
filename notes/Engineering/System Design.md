---
title: "System Design"
author: "Agastya Patel"
categories: [Notes, AI, Brief]
draft: true
---

> https://www.youtube.com/watch?v=m8Icp_Cid5o

Why System Design?
Large Scale Distributed System like Gmaps
- Lot of data
- High number of user
- CI/CD
- Performance expectation
The servers are located across the world

## Design patterns:
A software design pattern is a general reusable solution to commonly occurring problem within a given context of software design

> Eg: celeb posting post and being distributed to large number of users.

# Problem Statements
## Streaming/Video broadcasting

Requirements:
- Streaming Video
- Processing Video
- Broadcasting
- Failproof
- Advertisement
- Reactions
- Disclaimers/ News Flashes
- Degradation of Video Quality if low bandwidth
### Methods 
1. Being able to see the video is primary requirement
2. Reduce the feature/Abstract concepts
3. Create Data definition
4. Map into objects
- None of the services fail, failure safe
- Extensibility
> Build a system which can be scaled and extended when as the requirements changes
- Testing (capacity estimation)

Network Protocol : gRPC, http, ftp