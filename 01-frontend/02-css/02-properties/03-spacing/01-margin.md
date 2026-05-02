# CSS `margin`

## Визначення

**`margin`** — це властивість, яка визначає **зовнішні відступи елемента** (простір *поза* border).

Використовується для:

* відстані між елементами
* побудови layout
* вирівнювання

---

## Box Model контекст

```text
Content → Padding → Border → Margin
```

`margin` — **найзовнішній шар**

---

## Базовий синтаксис

```css
.box {
    margin: 20px;
}
```

---

## Скорочений запис (shorthand)

```css
margin: 10px 20px 30px 40px;
```

```text
top → right → bottom → left
```

---

### Варіанти

```css
margin: 10px;           /* всі сторони */
margin: 10px 20px;      /* top/bottom | left/right */
margin: 10px 20px 30px; /* top | left/right | bottom */
```

---

## Окремі властивості

```css
margin-top: 10px;
margin-right: 20px;
margin-bottom: 30px;
margin-left: 40px;
```

---

## Одиниці

```css
margin: 20px;
margin: 1rem;
margin: 5%;
```

---

`%` — від ширини батька (навіть для vertical margin!)

---

## Auto (дуже важливо)

```css
.box {
    margin: 0 auto;
}
```

Центрує елемент по горизонталі

---

### Умова

```css
width: 300px;
```

Працює тільки коли є ширина

---

### Flex/Grid магія

```css
.item {
    margin-left: auto;
}
```

push вправо

```css
.item {
    margin: auto;
}
```

повне центрування

---

## Negative margin

```css
.box {
    margin-top: -20px;
}
```

“затягує” елемент

---

### Використання

* overlap елементів
* fine-tuning layout

може ламати layout

---

## Margin Collapsing (дуже важливо)

---

### Що це?

Вертикальні margin можуть **зливатися**

---

### Приклад

```css
h1 {
    margin-bottom: 20px;
}

p {
    margin-top: 20px;
}
```

НЕ 40px → а 20px

---

### Правило

береться **більший margin**

---

## Коли НЕ працює collapsing

* flex container
* grid container
* position: absolute/fixed
* padding/border між елементами
* overflow: hidden

---

## Margin + display

---

### Block

```css
div {
    margin: 20px;
}
```

працює повністю

---

### Inline

```css
span {
    margin: 20px;
}
```

* horizontal працює
* vertical — ні

---

### Inline-block

працює повністю

---

## Margin vs Padding

| Margin               | Padding            |
| -------------------- | ------------------ |
| зовні                | всередині          |
| не впливає на фон    | впливає            |
| відстань між блоками | внутрішній відступ |

---

## Margin + width

```css
.box {
    width: 100%;
    margin: 20px;
}
```

overflow

---

## Logical properties (modern)

```css
margin-inline: 20px;
margin-block: 10px;
```

підтримка RTL/LTR

---

## Практичні приклади

---

### Центрування

```css
.container {
    width: 300px;
    margin: 0 auto;
}
```

---

### Відступи між елементами

```css
.item {
    margin-bottom: 16px;
}
```

---

### Stack pattern

```css
.stack > * + * {
    margin-top: 16px;
}
```

дуже популярний патерн

---

### Flex layout

```css
.nav {
    display: flex;
}

.menu {
    margin-left: auto;
}
```

---

## Часті питання на співбесіді

* що таке margin collapsing?
* margin vs padding?
* як працює margin: auto?
* чи можна negative margin?
* як працює margin у inline?

---

## Часті помилки

* не розуміють collapsing
* margin для layout (замість flex/gap)
* overflow через width + margin
* неправильне використання auto

---

## Best Practices

* використовувати gap у flex/grid
* використовувати margin для spacing
* уникати negative margin без потреби
* розуміти collapsing

---

## Висновок

`margin`:

* керує зовнішніми відступами
* впливає на layout
* має складну поведінку (collapsing)

---

