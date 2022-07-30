---
title: "Hugo basics"
---

## Front matter
Markdown files need front matter:
`---
`title: "Some blog post"`
`date: 2022-07-30T09:01:05+01:00`
`draft: false`  --> if false, will not be published yet
`---`

Other things that can go into the front matter:
**Cover image**
`cover:`
	`image: img/somepic.jpg`
	`alt: "This is alt text"`
	`caption: "This is the image caption"`

## Configuration file
Read theme documentation to know exactly what can be changed in the config.yaml file.

E.g. menu for "Categories" displayed (in PaperMod theme):

`menu:
	`main:
		`identifier: categories`
		`name: Categories`
		`url: /categories/`
		`weight: 10`


Then in the front matter of the "Categories" main .md page, add `layout: "categories"`  --> this only works if there is a categories.html template in the chosen theme (e.g. under static>themes>PaperMod>layouts)
`url: "/categories/"`
`summary: categories`
to the front matter below `title`.  


## Theme overwrites
Not recommended to directly update in the theme's files itself, otherwise the changes are lost when the theme is updated.
Better: make a local copy of the file that you want to change (e.g. archives.html). 
Go to your layouts folder and recreate the exact folder structure from your theme, leading to the archives.html file. 

Then whatever changes are done in _that_ file will overtake the settings in the original archives.html file. 

## Adding tags and categories to posts
_Theme-specific! Might not work in all themes!_

In front matter, add tags and categories as lists:
`tags: ["html", "css"]`
`categories: ["tech", "coding", "website"]`

## Show the path of a post/page
_Theme-specific! Might not work in all themes!_

In front matter, add:
`params:`
	`ShowBreadCrumbs: true`

## Changing header
Go to layouts > partials > header.html
Copy the file and insert (together with the proper folder structure) in your own layout folder.

Then change whatever you want in the copy file.