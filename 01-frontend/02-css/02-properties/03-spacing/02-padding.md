# CSS `padding`

## Визначення

**`padding`** — це властивість, яка визначає **внутрішні відступи елемента** (простір *між content і border*).

Використовується для:

* відступів всередині елемента
* збільшення “клікабельної зони”
* керування внутрішнім простором

---

## Box Model контекст

```text
Content → Padding → Border → Margin
```

`padding` знаходиться **між content і border**

---

## Базовий синтаксис

```css
.box {
    padding: 20px;
}
```

---

## Скорочений запис (shorthand)

```css
padding: 10px 20px 30px 40px;
```

```text
top → right → bottom → left
```

---

### Варіанти

```css
padding: 10px;           /* всі сторони */
padding: 10px 20px;      /* top/bottom | left/right */
padding: 10px 20px 30px; /* top | left/right | bottom */
```

---

## Окремі властивості

```css
padding-top: 10px;
padding-right: 20px;
padding-bottom: 30px;
padding-left: 40px;
```

---

## Одиниці

```css
padding: 20px;
padding: 1rem;
padding: 5%;
```

`%` — від ширини батька (навіть vertical)

---

## Вплив на розмір елемента

---

### content-box (default)

```css
.box {
    width: 200px;
    padding: 20px;
}
```

фактична ширина:

```text
200 + 40 = 240px
```

---

### border-box

```css
.box {
    box-sizing: border-box;
    width: 200px;
    padding: 20px;
}
```

ширина = 200px (padding включений)

---

## Padding НЕ може бути негативним

```css
padding: -10px; 
```

на відміну від margin

---

## Padding + background

```css
.box {
    padding: 20px;
    background: red;
}
```

фон включає padding

---

## Padding + width: 100%

```css
.box {
    width: 100%;
    padding: 20px;
}
```

overflow (якщо content-box)

---

## Logical properties (modern)

```css
padding-inline: 20px;
padding-block: 10px;
```

RTL/LTR підтримка

---

## Padding + inline елементи

```css
span {
    padding: 20px;
}
```

* горизонтальний працює
* вертикальний працює візуально, але може ламати layout

---

## Padding + height hack (aspect ratio)

```css
.box {
    width: 100%;
    padding-top: 56.25%;
}
```

16:9 ratio

---

## Практичні приклади

---

### Кнопка

```css
button {
    padding: 10px 20px;
}
```

---

### Card

```css
.card {
    padding: 20px;
}
```

---

### Click area

```css
a {
    display: inline-block;
    padding: 10px;
}
```

---

### Container

```css
.container {
    padding: 0 16px;
}
```

---

## Padding vs Margin

| Padding                 | Margin |
| ----------------------- | ------ |
| всередині               | зовні  |
| впливає на фон          | ні     |
| не може бути негативним | може   |

---

## Часті питання на співбесіді

* padding vs margin?
* чи входить padding у width?
* чи можна negative padding?
* як працює %?

---

## Часті помилки

* overflow через padding
* плутають margin і padding
* не використовують border-box
* padding замість gap

---

## Best Practices

* використовувати padding для внутрішніх відступів
* використовувати border-box
* використовувати rem
* не змішувати з margin хаотично

---

## Висновок

`padding`:

* керує внутрішнім простором
* впливає на розміри елемента
* важливий для UX і layout

---

