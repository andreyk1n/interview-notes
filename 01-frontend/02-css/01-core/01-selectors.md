# CSS Selectors

## Визначення

**CSS selectors** — це механізм, який дозволяє вибирати HTML-елементи для застосування стилів.

Вони визначають:

* **що саме стилізувати**
* **як саме знаходити елементи в DOM**

---

## Базовий синтаксис

```css
selector {
    property: value;
}
```

---

## Основні типи селекторів

### 1. Universal selector

```css
* {
    margin: 0;
}
```

Вибирає всі елементи

### 2. Type selector (за тегом)

```css
p {
    color: red;
}
```

Вибирає всі `<p>`

### 3. Class selector

```css
.button {
    background: blue;
}
```

Найпоширеніший селектор

### 4. ID selector

```css
#header {
    height: 100px;
}
```

Унікальний елемент

---

## Групування

```css
h1, h2, h3 {
    font-weight: bold;
}
```

---

## Комбінатори (Combinators)

### Descendant (пробіл)

```css
div p {
    color: red;
}
```

Всі `<p>` всередину `div`

### Child (`>`)

```css
div > p {
    color: red;
}
```

Тільки прямі діти

### Adjacent sibling (`+`)

```css
h1 + p {
    color: red;
}
```

Перший сусід після

### General sibling (`~`)

```css
h1 ~ p {
    color: red;
}
```

Всі сусіди після

---

## Attribute selectors

```css
input[type="text"] {
    border: 1px solid;
}
```

Варіанти:

```css
[a]              /* є атрибут */
[a="value"]      /* точне співпадіння */
[a^="start"]     /* починається */
[a$="end"]       /* закінчується */
[a*="part"]      /* містить */
```

---

## Псевдокласи (Pseudo-classes)

Стан елемента

### Інтерактивні

```css
a:hover {}
a:active {}
input:focus {}
```

### Структурні

```css
li:first-child {}
li:last-child {}
li:nth-child(2) {}
li:nth-child(odd) {}
```

### Логічні

```css
:not(.active) {}
:empty {}
```

### Form

```css
input:checked {}
input:disabled {}
input:required {}
input:valid {}
input:invalid {}
```

---

## Псевдоелементи (Pseudo-elements)

Частини елемента

```css
p::before {}
p::after {}
p::first-letter {}
p::first-line {}
```

---

## Специфічність (Specificity)

Визначає, який стиль застосовується

### Вага:

| Тип | Вага |
|-----|------|
| inline | 1000 |
| id | 100 |
| class / attr / pseudo-class | 10 |
| element | 1 |

Приклад:

```css
#id .class p {}
```

Вага: 100 + 10 + 1 = 111

---

## Важливість (!important)

```css
color: red !important;
```

Погана практика — використовувати рідко

---

## Cascade (каскадність)

Вплив:

* специфічність
* порядок
* !important

---

## Сучасні селектори

### :is()

```css
:is(h1, h2, h3) {
    color: red;
}
```

### :where()

```css
:where(.box) {
    margin: 0;
}
```

Має 0 специфічність

### :has() (parent selector)

```css
div:has(p) {
    border: 1px solid;
}
```

Вибір по дітях

---

## Практичні приклади

### BEM

```css
.block {}
.block__element {}
.block--modifier {}
```

### Глибокі селектори (антипатерн)

```css
div div div p {}
```

Важко підтримувати

---

## Performance

Швидкість селекторів:

1. ID
2. Class
3. Tag
4. Universal (найповільніший)

Але різниця мінімальна в сучасних браузерах

---

## Часті питання на співбесіді

* що таке CSS selector?
* специфічність?
* різниця між class і id?
* :nth-child vs :nth-of-type?
* що таке combinators?
* що таке pseudo-elements?

---

## Часті помилки

* надто складні селектори
* зловживання !important
* використання ID для стилів
* глибока вкладеність

---

## Best Practices

* використовувати класи (BEM)
* уникати складних селекторів
* контролювати специфічність
* мінімізувати !important
* писати читабельний CSS

---

## Висновок

CSS Selectors:

* основа стилізації
* визначають зв'язок CSS та HTML
* впливають на підтримку і масштабування

---

