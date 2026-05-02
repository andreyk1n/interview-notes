# CSS `color`

## Визначення

Властивість **`color`** визначає **колір тексту (foreground)** елемента.

Впливає на:

* текст
* text-decoration (частково)
* деякі SVG
* currentColor (важливо)

---

## Базовий синтаксис

```css
p {
    color: red;
}
```

---

## Формати кольорів

---

### Named colors

```css
color: red;
color: blue;
color: black;
```

~140 стандартних назв

---

### HEX

```css
color: #ff0000;
color: #000;
```

---

### HEX з прозорістю

```css
color: #ff000080;
```

останні 2 символи — alpha

---

### RGB

```css
color: rgb(255, 0, 0);
```

---

### RGBA

```css
color: rgba(255, 0, 0, 0.5);
```

---

### HSL

```css
color: hsl(0, 100%, 50%);
```

---

### HSLA

```css
color: hsla(0, 100%, 50%, 0.5);
```

---

### Сучасні формати (CSS Color Level 4)

```css
color: rgb(255 0 0 / 0.5);
color: hsl(0 100% 50% / 0.5);
```

новий синтаксис без ком

---

## Прозорість

---

### opacity vs alpha

```css
opacity: 0.5;
```

впливає на ВСЕ (текст + діти)

---

```css
color: rgba(0, 0, 0, 0.5);
```

тільки текст

---

## currentColor (дуже важливо)

```css
border: 1px solid currentColor;
```

бере значення з `color`

---

### Приклад

```css
button {
    color: red;
    border: 1px solid currentColor;
}
```

border теж red

---

## inherit / initial / unset

---

### inherit

```css
color: inherit;
```

бере від батька

---

### initial

```css
color: initial;
```

дефолт браузера

---

### unset

```css
color: unset;
```

inherit або initial

---

## Cascade і color

```css
body {
    color: black;
}
```

color — успадковується

---

## Color + SVG

```css
svg {
    fill: currentColor;
}
```

синхронізація з текстом

---

## Color + text-decoration

```css
a {
    color: blue;
    text-decoration-color: red;
}
```

---

## System colors (рідко)

```css
color: CanvasText;
```

---

## Accessibility (дуже важливо)

---

### Контраст

WCAG:

* нормальний текст → 4.5:1
* великий текст → 3:1

---

### Погано

```css
color: #ccc;
background: #fff;
```

---

### Добре

```css
color: #222;
background: #fff;
```

---

## prefers-color-scheme

```css
@media (prefers-color-scheme: dark) {
    body {
        color: white;
    }
}
```

темна тема

---

## CSS Variables (для кольорів)

```css
:root {
    --primary: #3498db;
}

button {
    color: var(--primary);
}
```

---

## Практичні приклади

---

### Теми

```css
:root {
    --text: #000;
}

.dark {
    --text: #fff;
}

body {
    color: var(--text);
}
```

---

### Hover

```css
a {
    color: blue;
}

a:hover {
    color: red;
}
```

---

## Часті питання на співбесіді

* різниця rgba vs opacity?
* що таке currentColor?
* чи успадковується color?
* hsl vs rgb?
* як зробити темну тему?

---

## Часті помилки

* використання opacity замість rgba
* відсутній контраст
* жорстко захардкожені кольори
* ігнорування currentColor

---

## Best Practices

* використовувати CSS variables
* перевіряти контраст
* використовувати currentColor
* уникати opacity для тексту

---

## Висновок

`color`:

* базова властивість
* успадковується
* важлива для accessibility і theming

---

