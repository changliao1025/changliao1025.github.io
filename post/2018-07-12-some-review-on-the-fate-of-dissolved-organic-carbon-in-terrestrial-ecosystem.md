---
layout: post
title: Some review on the fate of dissolved organic carbon in terrestrial ecosystem
date: 2018-07-12 18:27:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Carbon
- DOC
- Hydrology
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
permalink: "/2018/07/12/some-review-on-the-fate-of-dissolved-organic-carbon-in-terrestrial-ecosystem/"
---
My recent modeling work involves some rewind of the process happened near the land surface, which causes some issue to the estimate of dissolved organic carbon (DOC) dynamics in terrestrial ecosystem.

I will skip the importance of DOC because you can find plenty of literatures online but instead I will focus on the challenge from a modeler's perspective.

First, we need to understand the source of DOC. Generally we think DOC is produced due to decomposition process and water flux. As we know, microbial decomposition occurs within nearly all places within the ecosystem: litter, soil and aquatic systems, etc. But water may not be present all the times in some ecosystem components.

In litter, decomposition is a continuous process through which fresh vegetation is transferred into organic carbon and enter into soil. However, a portion of the organic carbon may be transported through water flux in form of DOC during snowmelt, runoff and surface leaching. In this case, it is almost certain that the amount of DOC is influenced by not only the stage of decomposition, but also the amount of water flow.

As DOC flows into soil layer, it becomes part of soil DOC dynamics. Unlike litter, both decomposition and water flux are nearly always present even though the magnitude may be different.

When DOC enters into aquatic ecosystems (stream and lake, etc.), it may be consumed by the living organism within the systems. Also DOC may be directly produced within aquatic ecosystems.

Let's now consider the water movement, because of the hydrologic processes, DOC flows within the whole system. In each area, DOC is produced and consumed by various microbial activities. At the same time, there will be DOC flow in/out the domain (surface runoff, subsurface runoff, groundwater movement and surface leaching).

Taking all the above into consideration, DOC dynamics is each domain is a complex system (mixing of various concentration, microbial activity, biochemistry, etc.). As a result, modeling the fate of DOC dynamics in soil is difficult.

To tackle the difficulty, there are several steps we must take. First, we need to simulate the hydrological process with confidence; Second, we need to simulate all the flux of DOC within a domain (grid cell, etc.). Third, we need to simulate the DOC solute transport.

I will demonstrate how we did it in my future post.

