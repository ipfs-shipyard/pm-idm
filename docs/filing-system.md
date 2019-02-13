# Filing System

In order to keep the project organised, and so that everyone understands where and how to find the material, here's a detailed description of the folder structure to support the filing system.

## Folder structure

The folder structure is divided in several layers. Here's the layer breakdown:

**1. Client/organisation folders**

All new clients should get their own folders, even if they are related to the projects you’ve been working on earlier.

**2. Project folders**

Before you begin working on anything new, create a project folder with a meaningful name. `poster` is okay, but `halloween-poster-2018` is better, as you never know how many posters there will be down the road.

So what if you finish that project and the client returns months later asking for a revision? You’ll open up a new project folder named `halloween-poster-2019`. That way you’ll easily find the revision later, and keep track of everything your client ordered.

Folders roughly represent different development stages:

- `1_input`: Everything you use as input for the project, like briefing, inspiration, community feedback, raw footage and photography, templates that you buy, and other notes. This can contain files, documents, notes, etc.
- `2_work`: Where you keep the actual design or source files, the stuff you work on. Typically, it should contain nothing else but a list of files with the designs in various versions or revision stages.
- `3_output`: All final files for delivery to the next stage, should it be the development and marketing team, client, or other. For print projects, this is where you place your prepress files which can be sent to the printer, like PDF’s, fonts and so on. For web projects, this is where you put the mockups with specs, or actual HTML version of the site, if you do the coding too.

So, where will you find the photos that the client provided for the Halloween poster project? In the `1_input` folder. How about a file ready for printing? In the `3_output` folder.

## Versioning

Poor versioning typically looks like this:

- `Brochure Final.psd`
- `Brochure Final - image fix.psd`
- `Brochure Final Final.psd`
- `Brochure Final of all finals – cover page fix.psd`
- `Brochure Final Final Final.psd`
- `Brochure Final Final Final What Am I Doing.psd`

Considering the word `final` is very subjective and impractical, always use numeric versioning (revisions):

- `brochure_1.psd`
- `brochure_2.psd`
- `brochure_3.psd`

What happens if down the road, and let's say you're in revision `17`, and you absolutely want to go back to revision `9` and continue from there? Just copy revision `9` into a revision `18` and carry on from there.

Versions can be left padded with zeros, which holds no special meaning. `brochure_1.psd` is the same as `brochure_001.psd`. This is sometimes useful to keep files in natural order.

Besides revisions, every now and then you'll want to try and present different approaches at the same time. Let's say you were doing an halloween brochure, you might try two different concepts, one around *pumpkins* and another around *witches*:

- `brochure_4_pumpkins.psd`
- `brochure_4_witches.psd`

Once a decision is made, and an `alternative` is chosen, you can move on and create a new revision with `brochure_5.psd`.

Summing it up, our versioning system relies on 2 key elements, which are combined to organise the work:

- **Revision (mandatory)**: represents an iteration on the same concept.
- **Alternative (optional)**: represents a different concept or approach.

## Organising filing folders

Projects are typically composed of several subjects/sections, which then need to be organised. In order to avoid scalability issues, these folders follow a few conventions.

## Generic conventions

- **Allowed characters**: Whenever naming something, unless instructed otherwise, always use lowercase alpha-numeric characters and hyphens, **NEVER** spaces and underscores.
- **Subject folders:** If you need to group multiple subjects or sections that heavily relate to each other, by purpose or other criteria, name the sections and create folders for each. For instance, you could have the folders `artist-profile`, `library` and `account` inside the `2_work` folder, each representing different areas of the project.

## `1_input` conventions

Everything the client or any other stakeholder provides as input.

A few good ideas for folders inside this would be `client` (for client input), `inspiration` (for mood boards or other material that serves as inspiration). These are just suggestions, not mandatory.

## `2_work` conventions

- **File naming:** Files inside this folder follow the pattern `purpose_revision_alternative.extension`. Taking the `2_work/artist-profile` folder as an example, you could have a file named `homepage_13_light.psd`:
    - `purpose: homepage`: Sections typically have multiple purposes (possibly states). This file represents the `homepage` purpose. You could have something like `feed`, `videos`, `discography` here.
    - `revision: 13`: The revision number of the file.
    - `alternative: light`: You might need to create several approaches before deciding which one to take. This is where you can name that alternative. Avoid using colour names or anything else that you might want to change meanwhile and render the name useless. It's actually less confusing if you just name it alternative `a`, `b`, `c`, or instead name it with something semantically relevant for the reason of that approach, like `minimalistic` or `cartoonish`. Should be noted that alternatives are not themes, in the sense that they are competing, and only one will move forward. If both are moving forward, then they are themes, and you should put it in the `purpose`, not the `alternative`.
    - `extension: psd`: The extension of the file.

- **Canonical files:** Whenever you are working on a task that uses pre-existing or pre-produced assets, you should copy the canonical files into your subject folder, and keep working from there. The canonical files can either be somewhere inside `2_work`, or `1_input`. The goal is to keep canonical versions untampered, and have a single source of truth, so that any revisions of these canonical versions does not compromise pre-existing work, and also that some unrelated work contaminates the canonical files.

## `3_output` conventions

- **Consistent naming:** When exporting to `3_output`, it's up to you to decide whether to version the files or not. Be sensitive of who and when the next person will receive this output, and whether it might be easier or required to explicitly version the file (with revision AND/OR alternative). As a thumb rule, if you are versioning output, please keep up to 3 versions, so that we don't have an ever growing repository of outdated files.
- **Subject folders:** When possible, try to follow the same organisation you have on the `3_work` folder.

## Example

Here's a simplified, hypothetical organisation:

    - /
    	- **in-house** `pseudo-client used for in-house projects`
    		- company-website
    			- 1_input
    			- 2_work
    			- 3_output
    	- some-client
    		- some-project
    			- 1_input
    				- briefing.md
    				- community
    				  - user-survey-20180629.xls
    				- inspiration
    				  - awesome-similar-project.jpg
    			- 2_work
    				- logo
    					- logo_1.ai
    					- logo_2.ai
    				- backgrounds
    				- team-pictures
    				- icons
    				- experimentation
    					- poc_1.psd
    					- poc_2.psd
    					- poc_3_light.psd
    					- poc_4_dark.psd
    					- poc_5.psd
    				- desktop
    				  - account
    					  - ...
    					  - orders_7.psd
    					  - details_3.psd
    				  - artist-profile
    				  - library
    				- mobile
    				  - account
    				  - artist-profile
    				  - library
    			- 3_output
    				- desktop
    					- account
    						- orders_5.png
    						- orders_6.png
    						- orders_7.png
    						- details_3.png
    					- artist-profile
    					- library
    				- mobile
    					- account
    					- artist-profile
    					- library
    		- some-other-project
    			- ...

## Acknowledgements

This document is based on [How to keep your design files neat and tidy](http://99designs.com/designer-blog/2013/02/06/how-to-keep-your-design-files-neat-and-tidy/).
Contributors to this process were MOXY, Protocol Labs and BABOOM.