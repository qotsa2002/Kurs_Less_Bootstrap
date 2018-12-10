# Kurs Less und Bootstrap 3
Kurs vom 10.-11.12.2018

## Überblick
* Bootstrap - Hintergrund und Verwendung; Version 3.3.7 in der DATEV
* LESS - CSS-Präprozessor mit z.B. Variablen; Basis für Bootstrap

### Modulares CSS
#### SMACSS - Scalable and modular Architecture for CSS
https://smacss.com/

#### BEM - Block Element Modifier
http://getbem.com/introduction/

#### Wozu?
* Wartbarkeit
  * wozu dient etwas?
  * wie stark gekoppelt?
  * wie allgemein?
  * Nebenwirkungen?
  * modifizierbar? (Dynamik)
  * Erweiterbarkeit (Verkapselung)

#### Modular?
* "Modul" - benannte Einheit
* "Elemente" - aus diesen setzt sich ein Modul zusammen; hat eine Rolle; gehört zu __diesem__ Modul
* "Modifier" - beeinflussen die Darstellung von Elementen/Modulen; gehört zu __diesem__ Modul

#### Problembeispiel
```html
<div class="modulX">
    <h1> ... </h1>
</div>
```

```css
.modulX h1 {...}

.modulX h1.hover {...}
```

Problem: wirkt auf alle h1 innerhalb von modulX (auch verschachtelt)

==> nur mit Klassen arbeiten!

#### SMACSS Beispiel

```css
.myNodule {...}

.myModule-condensed {...} // modifier für Modul

.myModule_rolle {...} // _rolle z.B. _header

.myModule_rolle_modifier {...} // _modifier z.B. _hovered
```

__Wichtig__: Reihenfolge

Klassen ohne attribut-Definition als Identifikatoren (für Tests)



## Diverses

1em / 1rem - je nach Browser, nicht alle können rem

`document.getElementsByClassName` / `getElementById` --> Array mit allen Elementen der gleichen Klasse / letztes Element mit der Id

`document.querySelector('.classname');` liefert ersten node

`document.querySelectorAll('.classname');` liefert node-list


