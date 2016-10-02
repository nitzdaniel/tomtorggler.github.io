---
layout: post
title: "Azure File Services"
date: 2016-03-07 17:45:50 +0100
comments: true
published: true
categories: ["blog", "archives"]
excerpt_separator: <!-- more -->
tags: ["Azure"]
alias: ["/post/Azure-File-Services.aspx", "/post/azure-file-services.aspx"]
---
<!-- more -->
{% include imported_disclaimer.html %}
<p>Today I mapped an Azure File Share to my local computer <img class="wlEmoticon wlEmoticon-smile" style="border-top-style: none; border-left-style: none; border-bottom-style: none; border-right-style: none" alt="Smile" src="/assets/wlEmoticon-smile_3.png"> First you have to create a Storage account and a File Service</p> <p><a href="/assets/image_690.png"><img title="image" style="border-top: 0px; border-right: 0px; background-image: none; border-bottom: 0px; padding-top: 0px; padding-left: 0px; border-left: 0px; margin: 0px; display: inline; padding-right: 0px" border="0" alt="image" src="/assets/image_thumb_688.png" width="244" height="122"></a></p> <p>Within the Webinterface you can create folders and upload files</p> <p><a href="/assets/image_691.png"><img title="image" style="border-top: 0px; border-right: 0px; background-image: none; border-bottom: 0px; padding-top: 0px; padding-left: 0px; border-left: 0px; display: inline; padding-right: 0px" border="0" alt="image" src="/assets/image_thumb_689.png" width="244" height="131"></a></p> <p>When you click on “Connect” you can get the commands to map the volume. Its basically a normal Network drive.</p> <p><a href="/assets/image_692.png"><img title="image" style="border-top: 0px; border-right: 0px; background-image: none; border-bottom: 0px; padding-top: 0px; padding-left: 0px; border-left: 0px; margin: 0px; display: inline; padding-right: 0px" border="0" alt="image" src="/assets/image_thumb_690.png" width="244" height="80"></a></p> <p>The access key can be taken from the Settings / Key section</p> <p><a href="/assets/image_693.png"><img title="image" style="border-top: 0px; border-right: 0px; background-image: none; border-bottom: 0px; padding-top: 0px; padding-left: 0px; border-left: 0px; margin: 0px; display: inline; padding-right: 0px" border="0" alt="image" src="/assets/image_thumb_691.png" width="229" height="244"></a></p> <p>If you execute the command or simply mount the network volume you have the Azure File Service connected as Volume.</p> <p>Greetings<br>dn</p>