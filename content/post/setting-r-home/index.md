---
title: 'Setting the R home location using the .Rprofile'
subtitle: ''
summary: 
authors:
- seth-younger
tags:
categories:
date: "2020-05-04T00:00:00Z"
lastmod: "2020-05-04T00:00:00Z"
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
image:
  placement: 2
  caption:
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

The .Rprofile file provides a way to customize startup by setting a large variety of options. 
Setting the home directory is a useful option, it allows for the use of relative paths, which help access files stored in shared folders from many different computers without editing paths for each computer. 
OS X and Linux operating systems have their default home directory set to the location of Dropbox, Google Drive, Documents, etc., so it usually doesn't need to be modified for those operating systems. 
Windows computers don't default to the same home directory, so we need to modify the .Rprofile. It is usually found in the Documents folder on windows. To edit the file '.Rprofile' by right clicking and 'edit in' notepad or whatever text editor your have. After editing paths to match those of your computer, save it in 'C:\Users\USERNAME\Documents'. Where USERNAME is the windows user name on the computer you are working on.
If R is open close it and reopen it and relative paths to Dropbox should work.
You can test that it works by typing setwd('~/Dropbox') in the R console.

Here's an example of an Rprofile with the .First setting the Sys.env() parameter.

```r
.First <- function() {

# set the home directory so Dropbox is in the default search path
# this way any files that are read from Dropbox, Github, Google Drive, etc. work on all of my computers
Sys.setenv(R_USER="C:/Users/USERNAME")
    
}
```
There's more information about customizing startup here, https://www.statmethods.net/interface/customizing.html
