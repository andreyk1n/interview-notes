# CSS Flexbox (Flexible Box Layout)

## Визначення

**Flexbox** — це одновимірна модель layout у CSS, яка дозволяє **гнучко розташовувати елементи в рядку або колонці**, контролюючи їх розміри, порядок і вирівнювання.

Основна ідея:

* контейнер керує дочірніми елементами
* елементи адаптуються до доступного простору

---

## Основні поняття

### Flex Container

```css
.container {
    display: flex;
}
```

### Flex Items

```html
<div class="container">
    <div class="item"></div>
    <div class="item"></div>
</div>
```

Тільки **прямі діти** стають flex-елементами.

---

## Осі (Axes)

### Main axis (головна вісь)

Напрямок елементів.

### Cross axis (перпендикулярна вісь)

Поперечна вісь.

---

## flex-direction

```css
.container {
    flex-direction: row;
}
```

| Значення | Опис |
|----------|------|
| row | зліва → направо |
| row-reverse | справа → наліво |
| column | зверху → вниз |
| column-reverse | знизу → вверх |

Змінює main axis.

---

## justify-content (по main axis)

```css
.container {
    justify-content: center;
}
```

| Значення | Опис |
|----------|------|
| flex-start | початок |
| flex-end | кінець |
| center | центр |
| space-between | між |
| space-around | навколо |
| space-evenly | рівномірно |

---

## align-items (по cross axis)

```css
.container {
    align-items: center;
}
```

| Значення | Опис |
|----------|------|
| stretch | розтягнути (default) |
| flex-start | зверху |
| flex-end | знизу |
| center | центр |
| baseline | по тексту |

---

## align-content (для кількох рядків)

```css
.container {
    align-content: space-between;
}
```

Працює тільки з `flex-wrap`.

---

## flex-wrap

```css
.container {
    flex-wrap: wrap;
}
```

| Значення | Опис |
|----------|------|
| nowrap | в один рядок |
| wrap | перенос |
| wrap-reverse | знизу вверх |

---

## gap

```css
.container {
    gap: 10px;
}
```

Відступи між елементами.

---

## Властивості елементів (items)

### flex-grow

```css
.item {
    flex-grow: 1;
}
```

Розтягується.

---

### flex-shrink

```css
.item {
    flex-shrink: 1;
}
```

Стискається.

---

### flex-basis

```css
.item {
    flex-basis: 200px;
}
```

Початковий розмір.

---

### flex (shorthand)

```css
.item {
    flex: 1 1 200px;
}
```

---

### order

```css
.item {
    order: 2;
}
```

Змінює порядок.

---

### align-self

```css
.item {
    align-self: center;
}
```

Override align-items.

---

### Auto margins (магія)

```css
.item {
    margin-left: auto;
}
```

Push вправо.

---

## Приклади

### Центрування

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

### Space between

```css
.container {
    display: flex;
    justify-content: space-between;
}
```

### Sidebar layout

```css
.container {
    display: flex;
}

.sidebar {
    width: 250px;
}

.content {
    flex: 1;
}
```

---

## Flex vs Grid

| Flex | Grid |
|------|------|
| 1D | 2D |
| прості layout | складні layout |

---

## Часті питання на співбесіді

* Що таке flexbox?
* Main axis vs cross axis?
* justify-content vs align-items?
* flex-grow vs flex-basis?
* Flex vs grid?

---

## Часті помилки

* Плутають осі
* Використовують align-content без wrap
* Не розуміють flex: 1
* Margin замість gap

---

## Best Practices

* Використовувати для layout
* Використовувати gap
* Не зловживати order
* Комбінувати з grid

---

## Висновок

Flexbox — гнучкий layout, простий для більшості задач і основа сучасної верстки.

