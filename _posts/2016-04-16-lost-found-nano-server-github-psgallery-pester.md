---
layout: post
title: "lost & found: Nano Server, GitHub, PSGallery, Pester"
date: 2016-04-16 16:55:00 +0200
comments: true
published: true
categories: ["blog", "archives"]
excerpt_separator: <!-- more -->
tags: ["en", "PowerShell"]
alias: ["/post/lost-found-Nano-Server-GitHub-PSGallery-Pester.aspx", "/post/lost-found-nano-server-github-psgallery-pester.aspx"]
---
<!-- more -->
{% include imported_disclaimer.html %}
<h1>Nano Server status update</h1> <p>It would be about time for the next post in the series about hyper-converged-infrastructure with Nano Server. Over the past few days I deployed Nano on some real hardware and I can't wait to share my findings. But, unfortunately I'm facing a few issues, probably related to hardware, with the lab servers and I didn't have a lot of time to investigate further. As TP5 should be out any day now, I decided to wait for that before wasting too much time. </p> <h1>GitHub</h1> <p>In the meantime I have started to move some of my PowerShell scripts to GitHub for source control and publish them to the PowerShell Gallery for easy installation. I thought it might be interesting to share my process, so here we go.</p> <p>First of all, I’m not your typical developer, so I had a general idea about source control and I knew GitHub existed but never really used it, much less with PowerShell. The ongoing discussions about Continuous Integration and DevOps and what not, sparked my interest and so I decided to give it a try. The benefits of putting scripts under version control are obvious, the more you commit, the more history you get and the easier it gets to track code changes and errors. Additionally I really enjoy the community that has formed around PowerShell and publishing code to GitHub is one of many ways to contribute and give back to said community.</p> <p>Should you like to get started with git and don’t now where to start, <a href="http://mikefrobbins.com/2016/01/21/getting-started-with-the-git-version-control-system/" target="_blank">this article</a> helped me a lot when setting it up on my machines.</p> <p>And you can find my stuff at: <a title="https://github.com/tomtorggler" href="https://github.com/tomtorggler">https://github.com/tomtorggler</a></p> <h1>PowerShell Gallery</h1> <p>In case you didn’t know, Windows 10 (actually WMF5) comes with package management, yes that’s right, kind of like you know it from Linux or OSX. OneGet was introduced a while ago and eventually evolved into the PackageManagement module that is now included in <a href="https://www.microsoft.com/en-us/download/details.aspx?id=50395" target="_blank">WMF5</a>. The PSGallery is already configured as a PackageSource and can therefore be used right away. Just try Find-Script or Find-Module and install whatever you find interesting with Install-Script or Install-Module. Now anyone can publish scripts to this PSGallery thing, which is exactly what I did with <a href="/page/PS-Invoke-SEFAUtilps1.aspx" target="_blank">Invoke-SEFAUtil.ps1</a> and <a href="/page/PS-Restore-VMPermissionps1.aspx" target="_blank">Restore-VMPermission.ps1</a>.</p> <p>Other Package Sources can obviously be added, find out more at: <a title="https://msdn.microsoft.com/en-us/powershell/wmf/oneget_cmdlets" href="https://msdn.microsoft.com/en-us/powershell/wmf/oneget_cmdlets">https://msdn.microsoft.com/en-us/powershell/wmf/oneget_cmdlets</a></p> <h1>Pester</h1> <p>Along with the move to GitHub I started to write some Unit Tests for my code. So what does that mean? Well I told you, I’m not your typical developer so I’m still figuring this thing out :) The basic idea of unit testing is to write additional code that tests your code automatically. So when you change something in a script, you run the tests and if everything is green, the script is ready to go into production. </p> <p><a href="https://github.com/pester/Pester" target="_blank">Pester</a> is a unit testing framework for PowerShell, that can be used to achieve exactly that. Once I have found out enough to explain it in a better way, there might be a dedicated post :)</p> <p>&nbsp;</p> <p>With that, have a great weekend!</p> <p>Tom</p>