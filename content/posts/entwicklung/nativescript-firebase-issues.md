---
title: "Gelöst: nativescript-firebase Problem bei app resume"
date: 2020-01-21T19:33:18+01:00
tags: [Programmieren,Nativescript,Android,Bugfix]
---

Push Notifications stehen bei mir seit meinen Cordova Zeiten unter einem schlechten Stern, obwohl sich hier viel getan hat. Dementsprechend ging auch bei der aktuellen Implementierung mit [Nativescript](https://www.nativescript.org/) und Angular nicht gleich alles glatt.

Beim aktuellen Problem ging es um seltsames Verhalten der App, nachdem die App aus dem Ruhezustand über eine Push Notification geöffnet wurde. Dies führte dazu das Angular Services nicht mehr reagierten, es wirkte sogar so als würden bei jedem Neustart Services dupliziert. Nach einem Start aus dem Ruhezustand über Push Notification funktionierten dann eigentlich alle von einer Push Notification ausgelösten Features nicht mehr zuverlässig.

Nachdem ich das Problem auch in einer kleinen [Beispiel App](https://github.com/000panther/nativescript-push-error) reproduzieren konnte, versuchte ich zuerst mein Glück mit einem [Bug Report](https://github.com/EddyVerbruggen/nativescript-plugin-firebase/issues/1533). Die Sache ließ mich aber doch nicht in Ruhe, und nach ein bisschen Recherche im Plugin Source Code kam ich darauf das das Firebase Plugin scheinbar beim Suspend im Hintergrund weiterläuft - im Gegensatz zur Angular App, die bei einer Push Notification zerstört und neu gestartet wird. 

[Meine aktuelle Lösung](https://github.com/000panther/nativescript-push-error/tree/resolved): Checken ob Firebase bereits initialisiert ist, falls ja den onPushMessageReceived Listener auf die aktuelle (gerade gestartete) Angular App bzw entsprechende Services umbiegen.

 