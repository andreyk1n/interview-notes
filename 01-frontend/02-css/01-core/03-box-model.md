# CSS Box Model

## Визначення

**Box Model** — це модель, яка описує, як браузер розраховує розміри та простір елемента.

Кожен HTML-елемент — це прямокутник, який складається з:

```text
Content → Padding → Border → Margin
```

---

## Структура Box Model

```text
+---------------------------+
|         Margin            |
|  +---------------------+  |
|  |      Border         |  |
|  |  +---------------+  |  |
|  |  |   Padding     |  |  |
|  |  |  +---------+  |  |  |
|  |  |  | Content |  |  |  |
|  |  |  +---------+  |  |  |
|  |  +---------------+  |  |
|  +---------------------+  |
+---------------------------+
```

---

## 1. Content

```css id="5e1m3p"
width: 200px;
height: 100px;
```

Внутрішній вміст:
- текст
- зображення

---

## 2. Padding

```css id="7k3h2v"
padding: 20px;
```

Внутрішній відступ:
- між content і border
- впливає на розмір елемента

---

## 3. Border

```css id="q4l8mn"
border: 2px solid black;
```

Обрамлення елемента

---

## 4. Margin

```css id="z9f0xb"
margin: 10px;
```

Зовнішній відступ:
- відстань між елементами

---

## Розрахунок розміру

### Default (content-box)

```css id="p2k9sr"
width: 200px;
padding: 20px;
border: 2px solid;
```

Фактична ширина:

```text
200 + 40 (padding) + 4 (border) = 244px
```

---

## box-sizing

### border-box

```css id="d8w7qn"
box-sizing: border-box;
```

Width включає:
- padding
- border

Фактична ширина = 200px

---

### content-box (за замовчуванням)

```css id="x6n2tf"
box-sizing: content-box;
```

---

## Рекомендація

```css id="best1"
*,
*::before,
*::after {
    box-sizing: border-box;
}
```

Найпопулярніший підхід

---

## Margin Collapsing

Вертикальні margin можуть "зливатися"

```css id="m1k9lp"
div {
    margin-top: 20px;
}
```

Два елементи:
- не додаються (20px + 20px ≠ 40px)
- береться більший

---

## Inline vs Block

### Block

```css id="b7l4zt"
div {
    width: 100%;
}
```

Займає всю ширину

---

### Inline

```css id="c2f8wx"
span {
}
```

- width/height не працюють
- padding працює частково

---

### Inline-block

```css id="i9v3dx"
display: inline-block;
```

Комбінує обидва

---

## Overflow

```css id="ovf1"
overflow: hidden;
overflow: scroll;
overflow: auto;
```

Що робити з переповненням

---

## Outline (не входить у box model)

```css id="out1"
outline: 2px solid red;
```

- не впливає на розмір
- використовується для focus

---

## Box Model + Positioning

- margin — зовнішній простір
- padding — внутрішній
- border — межа
- position — змінює поведінку

---

## Часті питання на співбесіді

- що таке box model?
- різниця content-box vs border-box?
- що входить у width?
- що таке margin collapsing?
- як працює padding?

---

## Часті помилки

- забувають про padding у width
- не використовують border-box
- плутають margin і padding
- не враховують collapsing

---

## Best Practices

- використовувати border-box
- уникати складних розрахунків
- контролювати margin
- використовувати padding для внутрішніх відступів

---

## Висновок

Box Model:
- визначає розміри елементів
- критично важливий для layout
- основа CSS верстки

---

