# Kurs Less und Bootstrap 3
Kurs vom 10.-11.12.2018

## Überblick
* Bootstrap - Hintergrund und Verwendung; Version 3.3.7 in der DATEV
* LESS - CSS-Präprozessor mit z.B. Variablen; Basis für Bootstrap

## Modulares CSS
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


## LESS

Precompiler `lessc`, Verwendung: `lessc css/beispiel1.less css/beispiel1.css`

* Variablen: @varname
* Funktionen: funkt(...)
* mixins: klassendefinitionen, deren Inhalt per "Inline" in andere Klassendefinitionen aufgenommen wird
* Namespaces: verschachtelte Struktur ('&' für Bezug auf Parent file:.)
* `@import` anderer less-Dateien
* Mediaqueries: `@media screen and (min-width: 480px) {...}` (= width > 480px)
  * auf zwei Hiearchiestufen: komplettes Layout in einer Regel, oder regeln für einzelne Layout-Elemente
* Generieren von Layout-Elementen über parameter im Klassennamen s. [Gridbeispiel](lessbsp/grid.less):

```less
.generate-columns(@n, @i:1) when (@i <= @n) {
    grid-col-@{i} {
        color: black;
        ...
    }

    // rekursiv
    .generate-columns(@n, (@i+1));
}

.generate-columns(4);
```
erzeugt grid-col-1 bis grid-col-4  

### Einstellungen:
* Workspace Settings:

{
    "less.compile": {
        "out": false,
        "main": "styles.less"
    }
}

* Settings in .less files:

// out: true / false / name of output file --> Änderung in dieser datei bewirkt Compilierung
// main: xyz.less     --> Änderung in dieser datei bewirkt Compilierung von xyz.less 




## Diverses

1em / 1rem - je nach Browser, nicht alle können rem

`document.getElementsByClassName` / `getElementById` --> Array mit allen Elementen der gleichen Klasse / letztes Element mit der Id

`document.querySelector('.classname');` liefert ersten node

`document.querySelectorAll('.classname');` liefert node-list


