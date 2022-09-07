---
# try also 'default' to start simple
theme: default
# apply any windi css classes to the current slide
class: 'text-center'
font-size: 20px
# https://sli.dev/custom/highlighters.html
highlighter: prism
# show line numbers in code blocks
lineNumbers: false
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS (experimental)
css: unocss
---

# Konzept - Einheitliche Oberfläche für den Admin

von Peter Egermann

---

# Aufbau

- Vorteile einer einheitlichen Oberfläche
- Umstellung auf Bootstrap 5.1
- Das allgemeine Layout
- Komponenten
- Layouts

<style>
li {
  margin-top: 10px;
  font-size: 20px;
}
</style>

---

# Vorteile einer einheitlichen Oberfläche

- Schnelleres Erstellen von Oberflächen
- Intuitive Bedienung der Oberfläche
- Visuell ansprechender

---

# Die Umstellung auf Bootstrap 5.1

- Verbesserung einiger CSS-Klassen
- Leichte Änderung von einigen Funktionalitäten
- Einführung neuer Komponenten

<br>
<v-click>
```ts
<div class="placeholder"></div>
```
<img src="/Placeholder-example.png" class="mt-5 h-40 rounded shadow" />
</v-click>
---

# Das allgemeine Layout


```html {all|1|2|3|4|5,7|6|8}
<Breadcrumbs>
<h3> Überschrift </h3>
<Service-URL>
<div> Error-Rendering </div>
<div class="container-fluid">
    <Content>
<div>
<script> </> <!--- JS sollte immer mit appendFile() angehangen werden>
```

---

# Das allgemeine Layout

<img src="/Layout_Example.png" class="mt-5 rounded shadow" />

---
layout: cover
---

# Komponenten
<style>
p{
  font-size: 25px
}
</style>
Wie sollen die wiederkehrende Komponente aussehen?

---

### Form-Panel

<div class="mt-5 mb-5">

- Hintergrund für unsere Inhalte

</div>

<div grid="~ cols-2 gap-2">
<div>

HTML
```html
<div class="form-panel">
  <!-- Content -->
</div>
```
</div>
<div>

CSS
```css
.form-panel {
    background: #ffffff;
    padding: 10px;
    box-shadow: 0 3px 2px #aab2bd;
    text-align: left;
    border-radius: 7px;
    margin-bottom: 10px;
}
```
</div>
</div>
<div>
<div v-click>
View
<img src="/form-panel.png" class="mt-2 rounded shadow" />
</div>
</div>
---

### Form-Row

<div grid="~ cols-2 gap-2">
<div>

HTML
```html
<div class="form-panel form-row">
  <!-- Content -->
</div>
```
</div>
<div>

CSS
```css
.form-row {
    justify-content: flex-start;
    display: flex;
    padding-left: 10px;
    padding-right: 10px;
}

.form-row > * {
    margin-right: 5px;
}
```
</div>
</div>
<div>
<div v-click>
View
<img src="/form-row.png" class="mt-2 rounded shadow" />
</div>
</div>
---

### Button-Panel

<div class="mt-5 mb-5">

- Ansammlung von Buttons in einer Reihe
</div>

<div grid="~ cols-2 gap-2">
<div>
HTML
```html
<div class="form-panel button-panel">
  <!-- Content -->
</div>
```
</div>
<div>
CSS

```css
.button-panel {
    justify-content: flex-end;
    display: flex;
    padding-left: 2px;
    padding-right: 2px;
    margin-bottom: 3px;
}

.button-panel > * {
    margin-right: 5px;
}
```
</div>
</div>

<v-click>
<div>
View
<img src="/button-panel.png" class="rounded shadow" />
</div>
</v-click>

---

### Tabellen

<div>

HTML
```html {all|1,14|2,13|3,7|8,12}
<div class="form-panel">
    <table class="table table-striped data-table">
    <thead>
        <tr>
            <th> </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td> </td>
        </tr>
    </tbody>
    </table>
</div>
```
</div>

---

### Tabellen

<div>

View

<img src="/Tabelle.png" class="rounded shadow" />
</div>

--- 

### Breadcrumbs
<div class="mt-5 mb-5">

- Einfache Navigation auf verschachtelten Seiten

</div>
<div grid="~ cols-2 gap-4">
<div>

CSS
```css
ol.breadcrumb {
    padding: 10px 16px;
    list-style: none;
    background-color: #eee;
    margin-bottom: 7px;
}
 
ol.breadcrumb li {
    display: inline;
    font-size: 15px;
    margin-right: 5px;
}
```
</div>
<div>

View

<img src="Breadcrumbs.png" class="rounded shadow" />
</div>
</div>

---

 ### Breadcrumbs

<div class="mt-5 center-div">
<img src="Breadcrumbs_beispiel.png" class="rounded shadow h-100" />
</div>

---
layout: cover
--- 

# Layouts
<style>
p{
  font-size: 25px
}
</style>
Welche Seitenstrukturen treten wiederholt auf? 

--- 

### Einspaltig

<div>

HTML
```html {all|1,5|2,4|3}
<div class="container-fluid">
    <div class="form-panel col-xs-12 col-lg-6">
        <form> </form>
    </div>
</div>
```
</div>

---

### Einspaltig

<div class="mt-5 mb-5">
 View-Alt
 </div>
<div class="center-div">
<img src="/only_form_horizontal_old.png" class="h-80 rounded shadow" />
</div>

---

### Einspaltig


<div class="mt-5 mb-5">
 View-Neu
 </div>
<div class="center-div">
<img src="/only_form_horizontal_new.png" class="h-80 rounded shadow" />
</div>

---

### Zweispaltig - getrennte Panels
<div>

HTML

```html {all|1,8|2,4|5,7}
<div class="container-fluid">
    <div class="form-panel col-xl-6 col-lg-12">
        <? Content Linke Spalte?>
    </div>
    <div class="form-panel col-xl-6 col-lg-12">
        <? Content Rechte Spalte?>
    </div>
</div>
```
</div>

---

### Zweispaltig - getrennte Panels

<div class="mt-5 mb-5">
 View
 </div>


<div class="center-div">
<img src="/Zweispaltig_einzeln.png" class="h-80 rounded shadow" />
</div>

---

<style>
.center-div {
  justify-content: center;
  display: flex;
}
</style>

### Zweispaltig - gemeinsames Panel
<div>

HTML

```html {all|1,10|2,9|3,5|6,8}
<div class="container-fluid">
    <div class="form-panel">
        <div class="col-xl-6 col-lg-12">
            <? Content Linke Spalte?>
        </div>
        <div class="col-xl-6 col-lg-12">
            <? Content Rechte Spalte?>
        </div>
    </div>
</div>
```
</div>

---

### Zweispaltig - gemeinsames Panel

<style>
.center-div {
  justify-content: center;
  display: flex;
}
</style>

<div class="mt-5 mb-5">
 View mit gemeinsamem Panel
 </div>


<div class="center-div">
<img src="/Zweispaltig_Gemeinsam.png" class="h-80 rounded shadow" />
</div>

---

### Zeilen

<div>

HTML

```html {all|1,8|2,4|5,7}
<div class="container-fluid">
    <div class="form-panel horizontal-form-row">
        <form> </form>
    </div>
    <div class="form-panel">
        <table> </table>
    </div>
</div>
```
</div>

---

### Zeilen

<style>
.center-div {
  justify-content: center;
  display: flex;
}
</style>

<div class="mt-5 mb-5">
 View-Alt
 </div>
<div class="center-div">
<img src="/filter_tabelle_etcd_old_2.png" class="h-95 rounded shadow" />
</div>

---

### Zeilen

<div class="mt-5 mb-5">
 View-Neu
 </div>
<div class="center-div">
<img src="/Layout_Example.png" class="h-95 rounded shadow" />
</div>
