---
layout: post
title:  "Design in Responsive Design verwandeln"
date:   2016-04-19 19:40:00 +0200
author: "Delite"
---
In diesem Tutorial zeige ich euch wie ihr aus einem normalen Design ein schickes Responsive-Design hinkriegt. Das Layout was ich dazu verwende habe ich vollkommen zufällig gewählt.

Als Beispiel nehme ich ein schönes Design von [The Pink Pearl](http://www.thepinkpearl.de/): [Fairy Tail Lucy Style](http://www.thepinkpearl.de/Designs/4961_view.html).

<div style="text-align:center"><img src="/images/placeit.jpg" /></div>

<div style="text-align:center"><small>Gemacht mit <a href="https://placeit.net">placeit</a></small></div>


## 1. Variable Breite setzen

{% highlight html %}
<meta name="viewport" content="width=device-width, initial-scale=1">
{% endhighlight %}

Damit eure Seite überhaupt flexibel ist, müsst ihr diesen Code in den `head`-Bereich eurer Seite ablegen.

## 2. Mobile Ansicht in Chrome

<div style="float:left;padding-right:10px;"><img src="/images/responsive_debug.png" width="180" /></div>

Damit ihr euer Layout aus mobiler Ansicht sehen könnt, gibt es ein Tool, dass euch z.B. Chrome bereitstellt (andere Browser wie Firefox können das auch). Damit ihr nicht jedes Mal euer Handy benutzen müsst, geht in Chrome auf:

`View > Developer > Developer Tools` (englisch)

`Ansicht > Entwickler > Entwickler Tools` (deutsch, vermutlich)

Dort ist ein Symbol, das wie ein Tablet und ein Handy aussieht (im Screenshot blau). Aktiviert diese Ansicht und ihr könnt verschiedene Geräte ausprobieren. Für meine Tests verwende ich z.B. das iPhone5.


## 3. Headerbild anpassen

Da ich von oben anfange ist unsere erste Baustelle der Header. Das Layout umschließt außerdem den Wrapper. Dieser hat bereits eine `max-width`, welche dafür sorgt, dass er nicht größer als das Headerbild wird. Damit er fluider ist, braucht er nur eine Breite von 100%.

{% highlight css %}
#wrapper {
  width: 100%;
}
{% endhighlight %}

Gleiches müssen wir auch für den Header machen, welcher auch bereits eine `max-width` von 1000px hat.

Allerdings haben wir jetzt das Problem, dass die Höhe nicht mehr im Verhältnis zum Headerbild steht. Um das zu erreichen gibt es einen kleinen Trick. Zuerst müssen wir das Verhältnis zwischen Höhe und Breite berechnen: (366/1000) ~ 36%. Dafür erstellen wir jetzt ein Pseudo-Element (`:before`), das dafür sorgt, dass die Höhe immer zur Breite passt.

Desweiteren müssen wir das Bild natürlich auch noch resizen. Das können wir mit der CSS3 Property `background-size` tun. Neben prozentualen oder Pixelwerten können wir hier einfach `cover` eingeben, welche unser Bild automatisch an die Größe anpasst. Cool.

{% highlight css %}
#header {
  background-image: url(images/header.png);
  background-position: right;
  background-size: cover;
  max-width: 1000px;
  width: 100%;
  position: relative;
}

#header:before {
  content: "";
  display: block;
  padding-top: 36%;
}
{% endhighlight %}

Das sieht dann schon mal so aus:


<div style="text-align:center;"><img src="/images/responsive1.png" width="160" /></div>


## 4. Content und Newsbox anpassen

Der Content brauch auch eine `max-width` und eine Breite von 100%. Außerdem brauch er ein anderes Box-Layout, da er ein `padding` definiert hat. Das normale Box-Model, das wir benutzen würde eine Breite von 100% nehmen und obendrauf noch `20px` von padding schlagen. Was wir aber wollen ist, dass in den 100% bereits dieses padding eingeschlossen ist. Das erreichen wir durch `box-sizing: border-box`:

{% highlight css %}
#content {
  max-width: 760px;
  width: 100%;
  box-sizing: border-box;
  -webkit-box-sizing: border-box;

  height: 100%;
  background-color: #ffffff;
  float: left;
  padding: 20px;
  font-family: Helvetica, Verdana;
  font-size: 13px;
  letter-spacing: 150%;
  line-height: 150%;
  color: #0c0c0c;
}
{% endhighlight %}

Darüber hinaus haben wir noch ein `blockquote`-Element, welches eine fixe Breite hat. Dies müssen wir ändern und da es auch ein Padding hat müssen wir `box-sizing: border-box` verwenden:

{% highlight css %}
blockquote {
  max-width: 600px;
  width: 100%;
  box-sizing: border-box;
  -webkit-box-sizing: border-box;

  padding: 20px;
  background-color: #c1d7ed;
  border: 1px solid #c0c0c0;
  margin: 0 auto;
  margin-bottom: 15px;
}
{% endhighlight %}

Das ist aber noch nicht alles. Desweiteren haben wir noch einen Banner in unserem Content, den Banner. Wir möchten, dass der Banner kleiner gemacht wird, wenn er zu groß ist. Dafür definiere ich eine neue CSS-Klasse:

{% highlight css %}
.img-fluid {
  max-width: 100%;
  height: auto;
}
{% endhighlight %}

und weise sie im HTML-Code zu:

{% highlight html %}
<img src="images/banner.png" class="img-fluid" />
{% endhighlight %}

Als nächstes ist die Newsbox dran:

{% highlight css %}
#newsskin {
  max-width: 640px;
  width: 100%;
  box-sizing: border-box;
  -webkit-box-sizing: border-box;

  background-color: #c1d7ed;
  border: 1px solid #c0c0c0;
  margin: 0 auto;
  margin-bottom: 15px;
}
{% endhighlight %}

Jetzt haben wir allerdings noch das Problem, dass das Updateicon und die Updatebox nebeneinander sind. Für die mobile Ansicht wollen wir sie untereinaner haben. Diese spezielle Ausnahme erstellen wir mit einem `media`-Query:

{% highlight css %}
@media (max-width: 620px) {
  #newsicon {
    float: none;
  }
  #newsupdate {
    float: none;
    width: auto;
    display: block;
    height: auto;
  }
  #newsupdate:before {
    content: '';
    display: block;
    clear: both;
  }
  #newscontent{
    margin-top: 10px;
  }
}
{% endhighlight %}

Wenn das Gerät kleiner als 620px ist, floaten wir den Avatar und die Updatebox nicht. Stattdessen fügen wir noch ein wenig Abstand hinzu.

Das Ganze sieht dann so aus:

<div style="text-align:center"><img src="/images/responsive2.png" width="160" /></div>

## 5. Footer anpassen

Im Footer haben wir zwei Spalten, eine für die Partner und eine für die Shoutbox. Auf der mobilen Ansicht wäre es super, wenn die zwei Spalten untereinander erscheinen. Dazu setze ich die Spalten erstmal auf 50% statt einem festen Pixelwert:

{% highlight css %}
#footerlinks, #footershouti {
  width: 50%;
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
{% endhighlight %}

Für Mobile erstelle ich dann wieder einen Media-Query und setze die Breite auf 100%:

{% highlight css %}
@media (max-width: 620px) {
  #footershouti, #footerlinks {
    width: 100%;
  }
}
{% endhighlight %}

Das Ergebnis sieht dann so aus:

<div style="text-align:center"><img src="/images/responsive3.png" width="160" /></div>

## 6. Navigation anpassen

Als erstes wollen wir die Navigation benutzbar machen. Dazu machen wir sie auf die volle Breite auf der mobilen Ansicht, die Abstände größer und setzen sie von der Reihenfolge nach oben (im HTML einfach die Navigation ausschneiden und vor dem content plazieren):

{% highlight css %}
@media (max-width: 800px) {
  #navigation {
    width: 100%;
  }
  #navigation #newsbox li a {
    width: auto;
    padding-top: 10px;
    padding-bottom: 10px;
  }
}
{% endhighlight %}

<div style="text-align:center"><img src="/images/responsive4.png" height="200" /> -&gt; <img src="/images/responsive5.png" height="200" /></div>

## 6. Navigation togglen lassen

Viele Websites verstecken das Menü auf der mobilen Ansicht, da es sehr viel Platz wegnimmt. Das können wir auch machen, indem wir einfach einfach eine Checkbox als toggle benutzen.

Dazu setzen wir eine Checkbox zwischen Header und Navigation:

{% highlight html %}
<div id="header"></div>

<input type="checkbox" id="mobile_nav_toggle" />

<div id="navigation">
  ...
</div>
{% endhighlight %}

Durch den Pseudo-Selektor `:checked` können wir jetzt die Navigation an und Ausschalten. Auf der Desktop-Größe verstecken wir einfach den toggle:

{% highlight css %}
#mobile_nav_toggle {
  display: none;
}
@media (max-width: 800px) {
  #navigation {
    width: 100%;
    display: none;
  }
  #navigation #newsbox li a {
    width: auto;
    padding-top: 10px;
    padding-bottom: 10px;
  }
  #mobile_nav_toggle {
    display: block;
  }
  #mobile_nav_toggle:checked + #navigation {
    display: block;
  }
}
{% endhighlight %}

Das sieht natürlich noch nicht schön aus, ist aber funktional ;)

<div style="text-align:center"><img src="/images/responsive6.png" height="200" /> <img src="/images/responsive7.png" height="200" /></div>

## 7. Toggle stylen

Dazu müssen wir ein `label`-Tag erstellen, welches auf den Toggle verweist. Dieses Label setzen wir unterhalb der Checkbox im HTML:

{% highlight html %}
<div id="header"></div>

<input type="checkbox" id="mobile_nav_toggle" />

<label for="mobile_nav_toggle" id="mobile_nav_toggle_label">
  Menü
</label>

<div id="navigation">
  ...
</div>
{% endhighlight %}

Im CSS machen wir jetzt unsere eigentliche Checkbox unsichtbar. Außerdem stylen wir unser Label und fügen einen Pfeil hinzu, der nach oben zeigt, falls das Menü schon geöffnet ist.

{% highlight css %}
#mobile_nav_toggle {
  display: none;
  width: 1px;
  height: 1px;
  opacity: 0;
}
#mobile_nav_toggle_label {
  display: none;
}
@media (max-width: 800px) {
  #navigation {
    width: 100%;
    display: none;
  }
  #navigation #newsbox li a {
    width: auto;
    padding-top: 10px;
    padding-bottom: 10px;
  }
  #mobile_nav_toggle {
    display: block;
  }
  #mobile_nav_toggle_label {
    display: block;
    text-align: center;
    background: #255da4;
    font-family: Helvetica, Verdana;
    text-transform: uppercase;
    color: #fff;
    padding: 10px;
  }
  #mobile_nav_toggle_label:after {
    content: '↓';
  }
  #mobile_nav_toggle:checked ~ #navigation {
    display: block;
  }
  #mobile_nav_toggle:checked ~ #mobile_nav_toggle_label:after {
    content: '↑';
  }
}
{% endhighlight %}

<div style="text-align:center"><img src="/images/responsive8.png" height="200" /> <img src="/images/responsive9.png" height="200" /></div>


## Schlusswort

Das Ergebnis:

<div style="text-align:center"><img src="/images/responsive_end.gif" /></div>

Alle Änderungen im Vergleich könnt ihr [hier](https://github.com/Delitecake/responsive-design-example/pull/1/files?diff=split) sehen.

Das Endergebnis könnt ihr [hier](https://github.com/Delitecake/responsive-design-example/archive/master.zip) als ZIP herunterladen oder [hier](https://github.com/Delitecake/responsive-design-example) einfach mal ansehen.
