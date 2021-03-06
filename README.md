# How to build a BEMO theme?

I'm just learning! These are some notes on my progress, this is not a how-to.

[Take a look to the the work in progress](http://spleenteo.github.io/test-material-bemo/)

# Goal

Build a [Material Design][material-design] CSS theme for [BEMO][bemo]

* I like [Google Material Design][material-design] and the css porting made by [Material Design CSS project][materializecss] 
* I love [BEMO](https://github.com/cantierecreativo/bemo) as [Sass][sass] bootstrap (filesystem structure and [BEM][bem] naming convention)
* I don't like the [MDcss][materializecss] css architecture and the way they named classes.

[bemo]: https://github.com/cantierecreativo/bemo
[sass]: http://sass-lang.com/
[bem]: https://bem.info/
[material-design]: http://www.google.com/design/spec/material-design/introduction.html
[materializecss]: http://materializecss.com/

# Why a theme

BEMO is growing up. I don't want to split the project. A theme should permit updating BEMO behind the scenes.

# Possible problems

* BEMO is not built to support themes.
* MD uses lot of JS scripts: are they linked to class names?
* If I'll be good enough to build the theme, how can it be install next to the standard BEMO?
* I would like to use BEMO's variables / mixins etc. and override my stuff only. Override attributes could be a pain in many cases...  

# Possibile solutions

* I'll just create HTML snippets to test classes and block to reproduce the styles. For the moment, I don't care of JS. Take it easy.
* I'll start with overrides... let's see how difficult it could be
* Mixins and functions are not a problem
* Variables might be defined for the theme... how?
* need to find MD font and icons...

# Let's start

I'm going to write down my progress. Good or bad, it doesn't matter!

* colors: MD usa una map list prticolare per definire i colori. una palette mastodontica. Crea anche delle classi per definire gli attributi color e bg-color. I colori hanno fino a 5 versioni di gradiente in chiaro e scuro. Sarebbe interessante riportarli tutti ma al momento prendo  solo i colori base.
* reported some horrible mixins to manage box shadows.
* no bourbon/compass, ho fatto animazioni con un mixin temporaneo
* creato blocco badge
* creato blocco bottoni normali. Finora usare l'override non mi ha creato problemi
* ho dovuto creare un file base per il tema
* ho dovuto fare degli import in applicatino sass in punti differenti. questo vorrei cambiarlo ma dubito si possa.
* ho finito i bottoni e finora il alvorod i override non ha dato alcun problema.
* ho fatto funzionare un js delle card. Tutte le calssi e il sistema di selector va rivisto. ho usato la convezione  ```.js-class-name``` da far masticare a jQuery. Sarebbe carino passare all'uso dei data attributes.
* Collections done without problems. I'm avoiding as much as I can MDcss variables, trying to use the BEMO's standard names.
* Footer component is done: they says they use flexbox for positioning but I can't find anything about that... wired.
* I'm thinking that maybe, the usage of classes to set elements color and float position is not so bad... OMG! It might be the fever...
* BOURBON: I tryed to avoid it but there are tons of transition; I'm using it just for that helper... easy to remove later.
* FORM: what a mess, there are tons of classes that can be bypassed. To rewrite everything is quite a big job. BEMO is ready to serve ```simple form``` classes. I have to move all those validation swooshes in different places to respect BEMO's default, that is much much easier to read and understand. I removed hundreds of css lines. Now, the problem will be the js... I'll see.
* ICONS: there 54Mb of glyphs... it has been sooo boring to select several versions (18px, 24px, 48px etc) for svg version, in order to use ```grunt bemo``` to create the icon font to be used. Now there are 759 elements. And I'm curious who is going to watch'em to choose the one he want to use! Naming convention of MD icons file, have been changed form ``ùnderscore```to ```dash```and I've used only 48px format, removing the size from the name. [Original package open source from goolge](http://www.google.com/design/spec/resources/sticker-sheets-icons.html#sticker-sheets-icons-components) or their [github repo](https://github.com/google/material-design-icons)
* 

