---
title: "Gelöst: nativescript-firebase Problem bei app resume"
date: 2020-01-21T19:33:18+01:00
tags: [Programmieren,Nativescript,Android,Bugfix]
---

Push Notifications stehen bei mir seit meinen Cordova Zeiten unter einem schlechten Stern, obwohl sich hier viel getan hat. Dementsprechend ging auch dieses Mal nicht gleich alles glatt.

Beim aktuellen Problem ging es um seltsames Verhalten der App nachdem die App aus dem Ruhezustand über eine Push Notification geöffnet wurde. Dies führte dazu das Services nicht mehr reagierten, es wirkte sogar so als würden bei jedem Neustart Services dupliziert. Nach einem Start aus dem Ruhezustand über Push Notification funktionierten dann eigentlich alle von einer Push Notification ausgelösten Sachen nicht mehr zuverlässig.

Nachdem ich das Problem auch in einer kleinen Beispiel App reproduzieren konnte, versuchte ich zuerst mein Glück mit einem Bug Report. Die Sache ließ mich aber doch nicht in Ruhe, und nach ein bisschen Recherche im Plugin Source Code kam ich darauf das das Firebase Plugin scheinbar beim Suspend im Hintergrund weiterläuft - im Gegensatz zur Angular App, die bei einer Push Notification zerstört und neu gestartet wird. 

Meine aktuelle Lösung: Checken ob Firebase bereits initialisiert ist, falls ja den onPushMessageReceived Listener auf die aktuelle (gerade gestartete) Angular App bzw entsprechende Services umbiegen.

 