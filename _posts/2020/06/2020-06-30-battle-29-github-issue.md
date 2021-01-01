---
layout: post
title: 'Battle 29: Github issue'
date: '2020-06-30T11:56:00.001-07:00'
author: Chang Liao
tags:
- Git
modified_time: '2020-06-30T12:28:43.828-07:00'
blogger_id: tag:blogger.com,1999:blog-3189999653395802666.post-7977886594119067448
blogger_orig_url: https://codedoesnotlie.blogspot.com/2020/06/battle-29-github-issue.html
---

<div><span style="background-color: #fafbfc; color: #586069; font-family: 
-apple-system, system-ui, &quot;Segoe UI&quot;, Helvetica, Arial, sans-serif, 
&quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;; font-size: 
14px;">This post is trying to resolve some common issues in my Github 
usage:<div><span style="background-color: #fafbfc; color: #586069; 
font-family: -apple-system, system-ui, &quot;Segoe UI&quot;, Helvetica, Arial, 
sans-serif, &quot;Apple Color Emoji&quot;, &quot;Segoe UI Emoji&quot;; 
font-size: 14px;"> 

<ul style="text-align: left;">1. This branch is 1754 commits behind 

<div>[https://www.quora.com/In-GitHub-how-do-I-resolve-the-issue-This-branch-is-n-commits-behind-master](https://www.quora.com/In-GitHub-how-do-I-resolve-the-issue-This-branch-is-n-commits-behind-master) 

It means your copy of the remote master branch (typically denoted as 
origin/master) has n commits more than your local version of the master 
branch. You can resolve this, while you have master checked out, by typing: 
git merge origin/master 

It's possible though that your copy of the remote branch is out of date as 
well, with more commits having been made since you fetched the copy you have. 
To update that, assuming your remote repository is labeled by default as 
origin, you can type: 
git fetch origin master 

Then you might see your local branch is even farther behind. Use the 
aforementioned merge command to update it. 

A shortcut that does the fetch and merge in one fell swoop, while you have 
master checked out, is: 
git pull 
<div> 
<div> 
<div><ul style="text-align: left;">1. Can I do some actions directly on 
Github? 

<div><ul style="text-align: left;">1. Should I clone a forked or the original? 