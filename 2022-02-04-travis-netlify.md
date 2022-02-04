---
title: "Travis CI and Netlify"
created_at: Fri Feb 4 2022 15:00:00 EDT
author: Montana Mendy
layout: post
permalink: 2022-02-04-travis-netlify
category: news
excerpt_separator: <!-- more --> 
tags:
  - news
  - feature
  - infrastructure
  - community
---

![fciyb5a398muulhutctz](https://user-images.githubusercontent.com/20936398/152582551-267e63bf-1a07-4a4f-af2c-7d54a5538fc5.jpeg)

CI/CD is an automated process, specifically a sequence of events -- that without it, you'd have to do manually and this sometimes strains resources. To make things easier we're going to use Netlify. Netlify discovers and installs your project dependencies and allows you to write powerful plugins that hook into any stage, so as you can see with Travis CI and Netlify, your project management will be highly automated, let's get started. 

<!-- more --> 

## Getting started

First lets disable Netlify's automatic builds so let's browse over to, `Build & Deploy > Continuous Deployment > Build Settings`. Now we need to fetch some of your `environment varibles`. So let's go to `Personal Access Token` and then select, `New Access Token`.

![image](https://user-images.githubusercontent.com/20936398/151615618-93853954-2162-4e62-9507-84659ae06151.png)


## Conclusion 

There you go, you just got an inside look on how flexible pull request management is in Travis! Now, take full advantage of your branches and workflow.

As always if you have any questions, any questions at all, please email me at [montana@travis-ci.org](mailto:montana@travis-ci.org).

Happy building!


<!-- more --> 

