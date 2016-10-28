---
layout: post
title: "Lync Private Line"
date: 2013-09-14 21:08:41 +0200
comments: true
category: Archive
tags: ["en", "Lync"]
redirect_from: ["/post/Lync-Private-Line", "/post/lync-private-line"]
author: thomas torggler
---
<!-- more -->
<p>I was at a customer’s site the other day when we he received the following request.</p>  <h1>Problem</h1>  <p>User A (the Boss) forwards his phone to User B (the Assistant). As someone calls the Boss, obviously the Assistants phone rings and she picks it up, it turns out the caller is important and needs to talk to the Boss. The Assistant transfers the call to the Boss… and that’s it. Since the Bosses phone is forwarded, nobody will be able to reach him.</p>  <p>Interestingly, in the ancient PBX world there was a “feature” (I’d call it bug) where the Assistant could “break through” the forwarding setting and therefore transfer calls to the Boss.</p>  <p>After bouncing some ideas we came up with a pretty simple solution. As the title implies, it makes use of Private Line feature in Lync 2013.</p>  <h1>Solution</h1>  <p>After some testing we configured a <a href="http://technet.microsoft.com/en-us/library/gg412728.aspx" target="_blank">Private Line</a> on the Bosses account and again, set up call forwarding to the Assistant in his Lync client.</p>  <p>Now, if someone calls the Boss, the Assistants phone would ring. If the caller wants to talk to the Boss, the Assistant can now simply forward the call to the Bosses private line. Call forwarding settings are not applied to this line, so his client would ring and he would be able to take the call. </p>  <h1>Alternative solutions</h1>  <p>Sure enough, there is no “one” solution, other possibilities would be the use of the Delegate or even Team Call features. In this particular case, though, we decided to use the Private Line.</p>  <p><strong>Update:</strong> Another solution for this particular problem would be to have the Boss configure the Assistant as his delegate, and the configure “Forward to Delegate” in her Lync Client. This enables User B to put calls through to User A, even though User A’s client is configured to forward calls.</p>  <p><a href="/assets/archive/image_568.png"><img title="image" style="border-top: 0px; border-right: 0px; border-bottom: 0px; border-left: 0px; display: inline" border="0" alt="image" src="/assets/archive/image_thumb_566.png" width="244" height="98" /></a> </p>  <p>You can use my <a href="/page/PS-Invoke-SEFAUtilps1.aspx" target="_blank">wrapper <u>script </u>for SEFAUtil</a> to configure this, too.</p>  <p><code>.\Invoke-SefaUtil.ps1 –Server ly15.tomt.local –UserName <a href="mailto:boss@tomt.it">boss@tomt.it</a> –AddDelegate <a href="mailto:assistant@tomt.it">assistant@tomt.it</a> –FwdToDelegates </code></p>  <p>Thanks to <a href="https://twitter.com/jpborth" target="_blank">@jpborth</a> for pointing this out!</p>  <h1>Configuration</h1>  <p>The Private Line feature requires Lync Server 2013, and is not exposed in the Lync Control Panel. The Set-CsUser cmdlet is used to configure a private line for a user:</p>  <p><code>Set-CsUser –Identity <a href="mailto:boss@uclab.eu">boss@uclab.eu</a> –PrivateLine “tel:+39123123”</code></p>  <p>Note: TechNet says, private line is new in Lync 2013, next time I’m in a pure 2010 environment, I’ll check if this feature can be configured on Lync 2010, too.</p>  <p>&#160;</p>  <p>so long,    <br />tom </p>
{% include imported_disclaimer.html %}