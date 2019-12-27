---
title: "Radlkarte Linz online"
date: 2019-12-25T08:33:18+01:00
tags: [Programmieren,Radfahren,Open Source]
description: Viel Arbeit aber auch viel Freude bereitete mir die Kartierung der Radinfrastruktur von Linz nach dem Vorbild der Radlkarte Wien
resources:
- name: radlkarte
  src: images/radlkarte.png
---

{{< figure src="/images/radlkarte.png" title="Radlkarte Linz" >}}

Ein Projekt das mir im letzten Vierteljahr viel Freude bereitet hat, war die [Kartierung der Radinfrastruktur von Linz](https://www.radlkarte.at/linz). Nach dem Schema der [Wiener Radlkarte](https://www.radlkarte.at) habe ich viele der Linzer Radrouten kartiert.

Schwierig war es Gebiete korrekt zu kartieren, wo ich selbst nicht so viel unterwegs bin. Ich habe versucht eine Grundinfrastruktur mithilfe des vorhandenen [W&amp;M Ökostadtplans](http://ooe.radlobby.at/karte/linz12/index.html?view=10203), der [OpenCycleMap](https://www.opencyclemap.org/) und Luftbildern von basemap.at nachzuziehen. Eine Erfahrung konnte ich dabei machen – gute Radinfrastruktur ist auch aus der Luft zu erkennen: Breite Radwege, gut sichtbare Blockmarkierungen oder rot eingefärbte Überfahrten. 

Die Karte wird von der Radlobby gehostet und ist auch auf Mobilgeräten funktionsfähig. Zusätzlich zur Kartenansicht gibt es eine „Wo bin ich“ Funktion und eine Adresssuche, sowie wechselbare Hintergrundkarten. Die Karte wurde mit Open-Source-Software umgesetzt und basiert auf der Wiener Radlkarte von Markus Straub. Die Hintergrundkarte basiert auf der frei verfügbaren [OpenStreetMap](https://osm.org).

Aktuell arbeite ich an einer Version mit Offline Support – mit Web Workern und einer statischen Hintergrundkarte als Fallback. Diese würde ich gerne auf jeden Fall unter 2 MB bekommen. Dazu experimentiere ich mit SVG und Maperitive herum ... 
