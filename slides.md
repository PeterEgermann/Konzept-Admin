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
- Vorher-Nachher Vergleich

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

# Das grundsätzliche Layout der Seiten

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

# Das grundsätzliche Layout der Seiten

<img src="/Layout_Example.png" class="mt-5 rounded shadow" />
---
 
# Komponenten

Um eine einfache Wiederverwendbarkeit von häufig auftretenden Elementen zu erreichen, wurden diese in Komponenten eingeordnet. 
### Form-Panel
Hintergrund für unsere Inhalte
<div grid="~ cols-2 gap-2">

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

<img src="/form-panel.png" class="mt-2 rounded shadow" />
</div>

---

### Button-Panel
Ansammlung von Buttons in einer Reihe

<div grid="~ cols-2 gap-2">

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

<img src="/form-panel.png" class="mt-2 rounded shadow" />
</div>