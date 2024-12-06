---
layout: niendefault
title: WATCH & GREP
category: "Dev Tutorial"
---
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
<a href="/tut" class="back-link">
  <i class="fa-solid fa-circle-left" style="color: #fff;"></i></a>

## watch and grep command

Date: 26/11/2024

#### watch command
 ```bash
 watch -n 0.1 ./your-script
 ```
 This is used to run a script over and over for every 0.1 seconds

#### watch and grep
```bash
 watch -n 2 'grep -H "availability" file1 file2 file3'
 ```