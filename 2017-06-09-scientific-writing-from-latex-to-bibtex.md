---
layout: post
title: 'Scientific writing: from LaTex to BibTex'
date: 2017-06-09 01:37:00.000000000 -07:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories: []
tags:
- Latex
- Mendeley
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
permalink: "/2017/06/09/scientific-writing-from-latex-to-bibtex/"
---
I am not very familiar with Tex system, but I use it for several purposes.

To produce a high quality manuscript using Latex itself can be a little bit of challenge so I am trying to do it once for all here.

Here are steps I generally follow if everything works fine.

1. You will need an [Overleaf](https://www.overleaf.com/)account because I prefer to write in a browser.
2. Find the template of the document. If Overleaf has one, use it directly, if not, download it and upload it as a project;
3. Start writing your manuscript just like normal;
4. For figures, I suggest use an separated folder and indexed names;
5. Use Mendeley to manage all your references and enable Mendeley Bibtex feature;
6. Connect your Overleaf with Mendeley,
7. Add the Bibliography file from Mendeley;
8. Add all citations into your manuscript;
9. Download the whole project including all output;
10. Install Bibtex on a Linux machine;
11. Upload all the results to Linux machine;
12. Install the&nbsp;[bibexport](http://www.ctan.org/pkg/bibexport)&nbsp;package;
13. Remove unwanted citations from the Mendeley local file using bibexport;
14. Upload the revised bib file back to Overleaf and update the project;
15. Congratulations.

Some tips are:

- Make sure you have cited all reference before you apply bibexport, or else you will have to repeat step 13 and 14 (because journal usually do not need your entire bib file and you must only include references that are actually cited.);
- Produce postscript format to prepare high quality figures if possible:
- Sometimes you have to disconnect Mendeley and re-connect again.

Good luck!

