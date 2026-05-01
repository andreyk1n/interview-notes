# CSS `display`

## Визначення

Властивість **`display`** визначає, **як елемент відображається в документі** та як він взаємодіє з іншими елементами в потоці.

Вона контролює:

* тип коробки (box)
* поведінку в layout
* участь у document flow

---

## Основні значення `display`

### 1. `block`

```css
div {
    display: block;
}
```

Особливості:

* займає всю доступну ширину
* починається з нового рядка
* підтримує width/height

Типові елементи: `<div>`, `<p>`, `<h1>`, `<section>`

### 2. `inline`

```css
span {
    display: inline;
}
```

Особливості:

* не переноситься на новий рядок
* ширина = контент
* width/height НЕ працюють

Типові елементи: `<span>`, `<a>`, `<strong>`

### 3. `inline-block`

```css
.element {
    display: inline-block;
}
```

Комбінація:

* як inline (в рядку)
* як block (можна width/height)

### Порівняння

| Властивість  | block | inline   | inline-block |
| ------------ | ----- | -------- | ------------ |
| Новий рядок  | Так   | Ні       | Ні           |
| width/height | Так   | Ні       | Так          |
| margin       | Так   | Частково | Так          |

### 4. `none`

```css
.element {
    display: none;
}
```

* елемент зникає
* не займає місце
* не існує в layout

### `visibility: hidden` vs `display: none`

| Властивість        | Видимість | Місце |
| ------------------ | --------- | ----- |
| display: none      | Ні        | Ні    |
| visibility: hidden | Ні        | Так   |

### 5. `flex`

```css
.container {
    display: flex;
}
```

Flexbox layout:

* одновимірний (row або column)
* вирівнювання і розподіл простору

Основні властивості: `justify-content`, `align-items`, `flex-direction`, `gap`

### 6. `grid`

```css
.container {
    display: grid;
}
```

Grid layout:

* двовимірний (rows + columns)
* точний контроль

Основні властивості: `grid-template-columns`, `grid-template-rows`, `gap`

### 7. `inline-flex` / `inline-grid`

```css
display: inline-flex;
display: inline-grid;
```

* як flex/grid
* але inline

### 8. `contents`

```css
display: contents;
```

* сам елемент "зникає"
* але діти залишаються

### 9. `list-item`

```css
li {
    display: list-item;
}
```

Додає маркер списку

### 10. `table` (legacy)

```css
display: table;
display: table-row;
display: table-cell;
```

Імітація таблиць

---

## Document Flow

* **Block flow**: елементи один під одним
* **Inline flow**: елементи в рядку
* **Flex/Grid**: кастомний layout

---

## Часті кейси

Центрування:

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

Горизонтальне меню:

```css
nav {
    display: flex;
    gap: 10px;
}
```

---

## Часті питання на співбесіді

* різниця block vs inline?
* що таке inline-block?
* display: none vs visibility?
* flex vs grid?
* що таке document flow?

---

## Часті помилки

* використання inline там де треба block
* неправильне розуміння inline-block
* зловживання display: none
* ігнорування flex/grid

---

## Best Practices

* використовувати flex для layout
* використовувати grid для складних структур
* не використовувати table layout
* правильно обирати display

---

## Висновок

`display`:

* визначає поведінку елементів
* впливає на layout
* є основою CSS

