---
layout: post
title: 'Ecosystem modeling: uncertainty quantification'
date: 2017-04-24 03:29:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags: []
meta:
  _publicize_pending: '1'
  restapi_import_id: 5caaaa8cc3ef2
  _import_original_post_id: '0'
author:
  login: changliao
  email: changliao1025@outlook.com
  display_name: Chang Liao
  first_name: ''
  last_name: ''
permalink: "/2017/04/24/ecosystem-modeling-uncertainty-quantification/"
---
I recently read a few news articles of skeptical attitudes towards climate change, and I decided to write something about it. I am not trying to promote climate change, but instead I want to point out there is great uncertainty in our current Earth system modeling.

Uncertainty quantification (UQ) is an important step in most numerical simulation processes. In general, a simulation without uncertainty quantification is less convincing. (I was surprised that an invited speaker in department seminar said he doesn't care about uncertainty.)

However, how to conduct uncertainty quantification itself is a challenge, especially for highly nonlinear ecosystem modeling.

First, I will invite you to read the Wikipedia UQ here:  
[https://en.wikipedia.org/wiki/Uncertainty\_quantification](https://en.wikipedia.org/wiki/Uncertainty_quantification)  
which serves as an overview of the concept I will discuss below.

Uncertainty comes from lots of sources and nearly every step we take in our Earth system modeling has uncertainty. We, scientists as well as engineers spent great efforts to reduce the uncertainty. That is why climate modelers always try to improving our estimates year by year. As a result. you may read papers like "something is potentially underestimated previously". (That is also why you see 7-day weather broadcasting is always changing.)

We don't know what we don't know. That is why we may never be able to consider everything, which is reasonable for scientific research. Decades ago, we didn't consider well the groundwater and surface water interactions in most hydrology modeling. Today, we still do NOT always consider!

Another big issue in Earth system modeling is that we are generally&nbsp;reluctant to spend too much efforts in UQ. Peer reviewers are not always interested in your UQ. However, they must be interested in your scientific questions and results. In an environment that publication is the major measure of your academic accomplishments, the quality of science is likely weakened.

Unlike experimental science, Earth system modeling is very much like a black box. Indeed you can see the source code of the model, but you can seldom reproduce the whole research since there are lots of pre-processes and post-processes involved but yet unveiled.

Assumptions. We made too many assumptions. There are many reasons we have to. One of the reason is the computational demand.

We always want more data. But the reason we need to simulate is we don't have enough data and there is also some data cannot be measured directly. Even we measured data, they are not true values in most cases.

If you look at the climate change prediction again, you can tell where the uncertainty comes from better.

1. We don't have high quality input data;
2. We made assumptions in lots of processes;
3. We ignored lots of processes;
4. We don't know lots of processes we don't know yet;
5. We made mistakes or even misconducts.

However, that is also why we are working hard to reduce the uncertainty. &nbsp;A few years back, the weather broadcast was as good as today's? I doubt.

