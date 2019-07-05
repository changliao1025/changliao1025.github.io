---
layout: post
title: 'Scientific writing: how to prepare a good image figure'
date: 2016-03-25 21:11:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Color
- Figure
- Image
- Writing
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
permalink: "/2016/03/25/scientific-writing-how-to-prepare-a-good-image-figure/"
---
"A picture is worth a thousand words", from [Wikipedia](https://en.wikipedia.org/wiki/A_picture_is_worth_a_thousand_words), unveils the importance of figures in writing.  
There are many types of figures or pictures, and in the field of Earth Science, image figure is one of the most important types.  
By image figure, I mean a figure composed of matrix, such as

 ![https://www.ncdc.noaa.gov/sotc/service/global/map-blended-mntp/201601.gif]({{ site.baseurl }}/assets/201601.gif)

[Link](https://www.ncdc.noaa.gov/sotc/global/201601) of the image.

(A selfie is also an image, but it is not commonly seen in scientific writing. Although the above figure is taken from the website, it is publication-ready in my opinion.)

So what makes a good&nbsp; image figure? The figure above actually gives a good example, and we can see what are the principle elements in this figure.

- A clear and concise title
- An appropriate map projection
- A beautiful color bar and data presentation
- Adequate description (data source, etc.)

Even without supplementary material, I believe most readers can understand this figure without difficulties.

So where are the challenges?   
Usually we can easily prepare the title, projection and description with care. The challenging part is the color presentation of the matrix data.

For example, if the above image is rendered using black and white, I think all of us will be disappointed (this is not photography).  
How about other color scale, such as from green to yellow? Maybe not a good idea.  
I think now we almost get to the point that colors matter.

We all know that nearly all colors can be decomposed into Red, Green and Blue and there is more than one million colors we can use. But in real life, we seldom need that much.  
A commonly used approach to get the best color for the data is using the color table, or the color look up table, through which only a number of colors (usually less than one thousand) are used for mapping.  
The selections of these colors are also based on a few approaches. Anyway, we can produce much nicer color tables such as this:

 ![]({{ site.baseurl }}/assets/BlAqGrYeOrReVi200_labelbar.500.png)

[Link](http://www.ncl.ucar.edu/Document/Graphics/color_table_gallery.shtml)of the image.  
The above color table contains exactly 200 colors. And if the matrix contains 200 unique values, the image would be perfectly displayed using these colors.

[![]({{ site.baseurl }}/assets/d4c02-matrix.png?w=300)](https://changliao.files.wordpress.com/2016/03/d4c02-matrix.png)

However, most of time, our data has way too many unique values. The stretch method is then used to scale our data before mapping them. There are also a few different stretch methods for different purposes. ArcGIS Map has some detailed explanation of these methods [here](http://desktop.arcgis.com/en/arcmap/10.3/manage-data/raster-and-images/stretch-function.htm).

Most of time, a linearly stretch will work, but sometimes, it does not work due to the data distribution.

However, when the data is stretched, we need to be careful with the color table. Because interpretation of the value from the color table need to be stretched as well. In this case, it has become not intuitive for us to guess the value from the map since its color may not be linearly stretched.

Then the classification method comes into the play. If we can classify the matrix data to a few classes, then it would be pretty straight forward to guess the value range from its color. Besides, classification means that we will only have a few colors, usually less than 20.

There are also quite a few methods of classification.

I will leave this work to the readers.

To be continued...

