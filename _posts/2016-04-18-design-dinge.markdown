---
layout: post
title:  "8 Dinge die man bei seinem Design beachten sollte"
date:   2016-04-18 20:20:48 +0200
author: "Delite"
---
Wenn man das erste mal eine Homepage erstellt, ist das Design was man dazu nimmt sicherlich das Wichtigste. Es drückt aus was meine Homepage ausmacht und gibt Besuchern den ersten Eindruck.

Dies ist ein Gastpost auf [pinkpearlinfo](http://pinkpearlinfo.blogspot.de/). Vielen Dank lulu &#9825;

## 1. Inspiration & Resources

Neben den vielen tollen Grafikseiten wie [The Pink Pearl](http://www.thepinkpearl.de/) gibt es auch noch andere nette Referenzen.

### Frameworks

- [Bootstrap CSS Framework](http://getbootstrap.com/), [Bootstrap V4 Alpha](http://v4-alpha.getbootstrap.com/)
- [Foundation](http://foundation.zurb.com/)
- [Semantic UI](http://semantic-ui.com/)
- [UIKit](http://getuikit.com/)

### Fonts

- [Google Webfonts](https://www.google.com/fonts)
- [Font Squirrel](https://www.fontsquirrel.com/)
- [Adobe Edge Web Fonts](https://edgewebfonts.adobe.com/)

### Icons

- [Font Awesome <3](https://fortawesome.github.io/Font-Awesome/)
- [icomoon.io](https://icomoon.io/)
- [We love icon fonts](http://weloveiconfonts.com/)
- [Fontello](http://fontello.com/)

### Layouts
- [themezy](http://www.themezy.com/)

### Bilder

- [brusheezy](http://www.brusheezy.com/)
- [vecteezy](http://www.vecteezy.com/)
- [pixabay](https://pixabay.com/de/)
- [e-shuushuu](http://e-shuushuu.net/)

### Farben

Die Farbwahl ist immer eine schwierige Geschichte. Hier können euch Portale wie [colourlovers](http://www.colourlovers.com/) helfen. Auch gibt es einige Tools die euch anhand von Gestaltungsregeln die perfekte Palette mischen: [coolors.co](https://coolors.co/) und [colorpicker](http://www.colorpicker.com/).

<div style='text-align:center'><img src='http://fs5.directupload.net/images/160417/fri8rnfs.png' /></div>

## 2. Dinge ausprobieren

Vor allen Dingen wenn man auch als Team an einem Layout bastelt, möchte man vielleicht auch kleinere Experimente machen oder sogar Code-Snippets teilen. Vielleicht seid ihr ja sogar eine Grafikseite und wollt Code-Snippets für eure Besucher verfügbar machen.

Dafür gibt es spannende Tools wie [jsfiddle](https://jsfiddle.net/), die es euch ermöglichen im Browser direkt HTML/CSS/Javascript auszuprobieren. Ihr könnt dort sogar fremde Snippets 'forken' d.h. selber weiterführen. Außerdem könnt ihr externe Bibliotheken wie JQuery einbetten oder sogar den Verlauf eures Snippets im Auge behalten. Darüber hinaus könnt ihr sogar mit mehreren Leuten gleichzeitig arbeiten. Ich habe hier z.B. eine [Pulse-Animation](https://jsfiddle.net/gyv7p6r5/3/) erstellt.

## 3. Lesbarkeit

Es gibt viele wichtige Guidelines in diesem Bereich. Vor allen Dingen wenn eure Seite aus viel Text besteht z.B. Blog oder Staffelpage, solltet ihr euch mal einige Best Practices aneignen.

Eine gute Sammlung einer solchen Guideline kann z.B. [in diesem Blog Post](http://blog.usabilla.com/8-guidelines-for-better-readability-on-the-web/) gefunden werden. Dieser Arikel ist zwar auf Englisch, sollte aber leicht verständlich sein.

Überlegt immer gut welche Schriftart und Schriftgröße ihr auf welchen Farben benutzt. Kontrast und Zeilenabstand spielen eine sehr große Rolle.

## 4. Hover und andere States

<img src='http://fs5.directupload.net/images/160417/3faiicnv.png' style='float:right;padding-left:15px;max-width:40%;' />

Heutzutage ist nichts wichtiger als Haptik auf unseren Seiten. Wir wollen keine eingefrorenen Seiten, sondern welche die auf unsere Interaktion reagieren. Unsere Seite soll ruhig wirken aber gleichzeitig dem Nutzer das richtige Feedback geben.

Wichtig hierzu sind z.B. hover-States bei Links - so merke ich heutzutage als User überhaupt, dass es ein Link ist. Eine Liste von sog. Pseudo-Classes findet ihr [hier](http://www.w3schools.com/css/css_pseudo_classes.asp).

Darüber hinaus haben viele Seiten heuzutage den sog. *Parallax* Effekt, der dem User Feedback beim Scrollen gibt. Zu diesem Thema gibt es zahlreiche Tutorials z.B. [dieses hier](http://keithclark.co.uk/articles/pure-css-parallax-websites/).

Seit CSS3 haben wir auch viele andere Möglichkeiten wie unsere Effekte aussehen könnten. Wir können Animationen und Transitionen im puren CSS schreiben. Tutorials und Beispiele findet ihr z.B. hier:

- [Original Hover Effects](http://tympanus.net/Tutorials/OriginalHoverEffects/index3.html)
- [css3-animation-examples](http://designscrazed.org/css3-animation-examples/)

## 5. Bildgrößen

Bei diesem Thema geht es weniger um die Dimensionen, sondern mehr um die Dateigröße. Bilder und Webfonts machen heutzutage den Großteil einer Website aus, wenn sie heruntergeladen wird. Auf eurem Mobiltelefonen habt ihr sicherlich schon gemerkt wie lange so etwas laden kann.

Um dem entgegen zu wirken solltet ihr immer eure Bilder gut komprimieren und dafür sorgen, dass sie gecached werden. Damit ihr versteht was die Probleme auf eurer Website sind, solltet ihr [Google PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) verwenden. Google gibt euch wichtige Tipps.

Wenn ihr dort die Probleme hebt, werdet ihr vermutlich zu mehr mobilen Visits kommen.

## 6. Unterschiedliche Gerätegrößen

<img src='http://fs5.directupload.net/images/160417/3lnd39s6.png' style='float:right;padding-left:15px;max-width:40%;' />

An dem Buzzword Reponsive Design kommt man heute schwer vorbei. Da immer mehr Leute mobile Geräte wie Smartphones und Tablets benutzen (oder sogar Uhren!). Wer schonmal Google Analytics auf seiner Seite aufgesetzt hat, weiss dass heutzutage viele Nutzer vom Handy kommen. Die meisten Frameworks liefern schon eingebaute Reponsive-Patterns und unterstützen sie.

Aber was bedeutet Responsive-Design und wie kann ich es einsetzen?

Das ist natürlich ein Thema für sich, was ich gerne weiter ausführe, wenn es jemanden interessiert ;)

Grob gesagt spielen die sog. [Media Queries](http://www.w3schools.com/cssref/css3_pr_mediaquery.asp) eine große Rolle. Benutzt ihr sie in eurem CSS Code könnt ihr Designs für betsimmte Gerätegrößen anwenden. z.B. könntet ihr auf Desktop zwei floatende DIVs mit der Breite von 50% haben und auf Mobile sind diese DIVs dann z.B. 100% breit. Es gibt einige [Standard-Patterns](https://responsivedesign.is/patterns) zu diesem Thema. Frameworks wie [Bootstrap](http://v4-alpha.getbootstrap.com/layout/overview/) geben euch auch viel Erklärung dazu.

## 7. Unterschiedliche Browser

<img src='http://fs5.directupload.net/images/160417/xal778st.jpg' style='float:right;padding-left:15px;max-width:40%;' />

Heutzutage sind nicht nur unterschiedliche Browser wichtig, sondern auch unterschiedliche Betriebssysteme. Selbst bei gleichen Browsern gibt es auf unterschiedlichen Geräten schon einige Unterschiede.

Ich würde immer empfehlen mindestens zwei unterschiedliche Browser auf eurem Computer installiert zu haben. Wenn ihr auf Nummer Sicher gehen wollt wie eure Seite auf unterschiedlichen Seiten ausschaut könnt ihr z.B. das kostenlose Tool [browserling](https://www.browserling.com/) benutzen. Dort könnt ihr unterschiedliche Kombinationen testen <3 

Außerdem gibt es hilfreiche Seiten, die euch sagen welche CSS-Eigenschaften wo funktionieren z.B. bei [caniuse](http://caniuse.com/).

*Profitipp:* Internetexplorer 8 und älter wird heute von kaum jemanden mehr unterstützt. Microsoft selbst hat den Support aufgegeben :O

## 8. Man lernt nie aus

Das Internet ist voll von zahlreichen spannenden Tutorials. Egal ob für Anfänger oder Fortgeschrittene. Ihr könntet z.B. Video-Tutorials von [udemy](https://www.udemy.com/courses/development/web-development/) ausprobieren. Dort gibt es auch einige deutsche & kostenlose.

Wenn ihr englisch sprecht und etwas tiefer eintauchen wollt, könntet ihr auch [codeschool](https://www.codeschool.com/) mal ausprobieren.

***

## Schlusswort

Euer erstes Layout begleitet euch eine ganze Weile. Meistens hat man sich sehr schnell an einem Layout sattgesehen, insbesondere wenn man es selbst erstellt hat. Daher ist es immer gut ein wenig Feedback einzuholen und eine objektive Checklist hervorzuhohlen.

Wenn ihr noch Fragen habt oder Themen, die ihr gerne vertiefen würdet, sendet mir doch eine Email an delitecake@gmail.com oder fügt einen Kommentar hinzu.

