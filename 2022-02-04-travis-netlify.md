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

First lets disable Netlify's automatic builds so let's browse over to, `Build & Deploy > Continuous Deployment > Build Settings`. Now we need to fetch some of your `environment varibles`. So let's go to `Personal Access Token` and then select, `New Access Token`, enter a quick description so you know what the access token is for, and let's generate it. 

## Getting Travis CI setup

Now that you have your access token, let's add that token to your `environment variables` in Travis now:

<img width="1426" alt="Screen Shot 2022-02-04 at 10 35 44 AM" src="https://user-images.githubusercontent.com/20936398/152584225-a748a2e0-6b01-4e76-9be7-9f0e6ed35e0d.png">

Click `Add`,  and there you have it. Your `environment varbiables` are set. Let's look at a sample `.travis.yml`: 

```yaml
language: node_js
cache:
  directories:
    - node_modules
script:
  - yarn test:unit
before_deploy:
  - npm install netlify-cli -g
  - yarn build
deploy:
  provider: script
  edge: true
  script: netlify deploy --dir=dist --prod
  on:
    branch: main
 ```
 
You'll notice in the `before_deploy` hook we are going to install the package `netlify-cli` globally, and in this case we are going to be using `yarn`, so we're going to tell Travis to run `yarn build` -- which in essence will start building and running your app on Netlify. Don't forget to run your tests locally if need be:

```bash
yarn test:unit
```

Travis CI is now on your Netlify app! To make sure, look for these following lines in your build log:

<img width="772" alt="Screen Shot 2022-02-04 at 10 44 16 AM" src="https://user-images.githubusercontent.com/20936398/152585379-a004e75c-64de-4106-b306-3a3d778bb532.png">

## Conclusion 

There you go, you just got an inside look on how fast Travis CI can be setup on Netlify, so why not give it a shot? 

As always if you have any questions, any questions at all, please email me at [montana@travis-ci.org](mailto:montana@travis-ci.org).

Happy building!

