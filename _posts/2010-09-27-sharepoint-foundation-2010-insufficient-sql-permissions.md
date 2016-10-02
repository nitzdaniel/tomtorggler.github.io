---
layout: post
title: "Sharepoint Foundation 2010, insufficient SQL permissions"
date: 2010-09-27 19:00:12 +0200
comments: true
published: true
categories: ["blog", "archives"]
excerpt_separator: <!-- more -->
tags: ["Sharepoint", "SQL"]
alias: ["/post/Sharepoint-Foundation-2010-insufficient-SQL-permissions.aspx", "/post/sharepoint-foundation-2010-insufficient-sql-permissions.aspx"]
---
<!-- more -->
{% include imported_disclaimer.html %}
<p>Wenn man Sharepoint Foundation 2010 mit den integrierten SQL Server 2008 Express installiert, hat man recht wenig Möglichkeiten Eigenschaften für den SQL Server zu definieren (Benutzerkonten, Logs, Backup).</p>  <p>Wenn man nun über das Management Studio eine Verbindung mit SQL Server herstellen möchte, kann es vorkommen, dass man selbst mit dem Farm-Administratorkonto keine Änderungen an den entsprechenden Datenbanken vornehmen kann. Ein Blick auf die verbunden Gruppen des Farm-Administratorkontos verrät, dass sich das Benutzerkonto nur in der Gruppe <strong>public</strong> befindet und somit keine Einstellungen ändern darf.</p>  <p><a href="/assets/image_274.png"><img style="background-image: none; border-right-width: 0px; padding-left: 0px; padding-right: 0px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px; padding-top: 0px" title="image" border="0" alt="image" src="/assets/image_thumb_272.png" width="244" height="219" /></a></p>  <p>Zudem ist kein Benutzerkonto ersichtlich mit dem man sich anmelden könnte um das Farm-Administratorkonto den entsprechen Gruppen zuzuweisen. Mit dem Benutzer SA kann man sich ebenfalls nicht anmelden, da der “SQL Server- und Windows-Authentifizerungsmodus” nicht aktiviert ist.</p>  <p>Der Grund dafür liegt hier: Wenn man Sharepoint Foundation 2010 über den Rechtsklick auf das Setup-File und “<strong>Als Administrator ausführen</strong>” installiert, wird das Produkt über das lokale Administratorkonto mit logischerweise den entsprechenden Administratorrechten installiert. Das wäre eigentlich auch kein Problem, wäre nicht die folgende Änderung ab SQL Server 2008 fest implementiert:</p>  <p>In den Versionen vor SQL 2008 wurde der Gruppe lokale Administratoren (die enthält wiederum den Domain-Admin und geg. andere Benutzer) das SQL Benutzerrecht <strong>sysadmin </strong>zugewiesen. Folglich konnte jeder Admin,die Datenbanken verwalten. Ab SQL Server 2008 erhält diese Gruppe nicht mehr das sysadmin-Recht. Bei der manuellen Installation von SQL wird man danach gefragt welche Benutzer das sysadmin-Recht erhalten sollen. Als die Installation mit der Option “<strong>Als Administrator ausführen</strong>” durchgeführt wurde, hat der lokale Administrator die sysadmin-Rechte erhalten.</p>  <p>Lösung: Wir erhalten mit dem Farm-Administrator Konto keine Ändern-Rechte in SQL, bis wir uns mit dem <strong>lokalen Administrator </strong>anmelden, Management Studio öffnen und den Benutzerkonten die entsprechenden Rechte zuweisen.</p>  <p>PS: Wenn die Datenbank in den <strong>Sinlge User Mode </strong>geschalten wird, erhält die Gruppe lokale Administratoren (folglich auch Domain-Admins) die sysadmin-Rechte.</p>  <p>Grüße    <br />dn</p>