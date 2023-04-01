---
layout: post
title:  "File System"
subtitle: "A file system storing data"
thumbnail: "/img/hdd.png"
date:   2021-12-01 08:00:00 -0600
categories: c 
tags: C
technologies: c
---
<link rel="stylesheet" href="/css/styles.css">
This is an implementation of a file system by the parameters specified by [Dr. Nathan Backman](https://www.bvu.edu/academics/faculty/nathan-backman) of [Buena Vista University](https://www.bvu.edu/).

Originally written with [@jackmford](https://github.com/jackmford) <img src="/img/github.png" class="inline-icon"/>

I spent Summer 2020 rewriting and improving the code to gain a deeper understanding of file systems.

Programming language: <img src="/img/c.png" alt="c programming" class="inline-icon"/>

## Design
Requirements of this project were to implement the following funcionalities of a file system:
* <span class="design-requirement">init</span> - setup file system for reading, writing, and storing data
* <span class="design-requirement">destroy</span> - save important file system pointers and info to disk on exit
* <span class="design-requirement">open/close</span> - enforce rules of opening and closing files; hand off pointers to file data blocks
* <span class="design-requirement">read</span> - algorithm for reading file data; parameters including bytes to read, output location
* <span class="design-requirement">write</span> - algorithm for writing file data using available file system blocks
* <span class="design-requirement">unlink</span> - remove a file from the file system and free its data blocks
* <span class="design-requirement">list files</span> - list file names of currently stored files

## Test Suite
As I rewrote the code, I wrote out a test suite extending the one we were provided. The test suite included tests such as:
* attempt to write one byte more than allocated to the file
* try opening a file more than once (not allowed in this file system)
* buffer over read of file bytes (reading more bytes than allocated to the file)
* try writing to a file without opening it first
* fill the file system then delete everything
  * ensure all the file system blocks get returned successfully
* many more...

## Greatest Challenge
The algorithms to handle free file system blocks (providing them to files and restoring them to a free state) was a significant challenge. 

I'd also say closing (destroying) the active *real* file and reopening it was challenging. This required a successful exit process storing data so the next time it was opened, the file system can resume right where it left off.

After much testing, I was curious what more I could do with this established, working file system I had. 

So, I turned it into an [Encrypted File System](/c/2021/12/11/tfs-cwad.html). <img src="/img/encrypt.png" alt="encrypted icon" class="inline-icon"/>

## Thanks
Thank you for checking out my File System project. Read about the [Encrypted File System](/c/2021/12/11/tfs-cwad.html)!

Best.

##### Links
<div style="font-size: 10px;">
<a target="_blank" href="https://icons8.com/icon/AZOZNnY73haj/github">GitHub</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
<br/>
<a target="_blank" href="https://icons8.com/icon/40670/c-programming">C Programming</a> icon by <a target="_blank" href="https://icons8.com">Icons8</a>
</div>

<style>
.design-requirement {
    font-family: 'Courier New', sans-serif;
    font-size: 20px;
    text-decoration: underline;
}
</style>
