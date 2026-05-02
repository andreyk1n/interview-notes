# CSS Grid (Сітковий розкладка)

## Визначення

**CSS Grid** — це двовимірна модель розкладки, яка дозволяє будувати інтерфейси, керуючи **рядами (rows)** і **колонками (columns)** одночасно.

На відміну від Flexbox (1D), Grid працює в **2 вимірах**:

* горизонталь
* вертикаль

---

## Як мислити Grid

Flexbox: контент визначає розкладку
Grid: ти **спочатку задаєш розкладку**, потім розміщуєш контент

---

## Основні поняття

### Grid Container

```css
.container {
    display: grid;
}
```

### Grid Items

```html
<div class="container">
    <div class="item"></div>
    <div class="item"></div>
</div>
```

Прямі діти контейнера.

---

## Grid Lines, Tracks, Cells

### Grid Lines

Лінії сітки, пронумеровані від 1.

```text
| 1 | 2 | 3 |
```

### Tracks (рядки/колонки)

Простір між лініями.

```text
Column Track
Row Track
```

### Cell

Перетин рядка та колонки.

---

## grid-template-columns

```css
.container {
    grid-template-columns: 200px 1fr 1fr;
}
```

Приклад:

```text
| 200px | 1fr | 1fr |
```

---

## grid-template-rows

```css
.container {
    grid-template-rows: 100px auto;
}
```

---

## fr (fraction)

```css
grid-template-columns: 1fr 2fr;
```

Пропорція 1:2. Розподіляє вільний простір.

---

## gap

```css
.container {
    gap: 20px;
}
```

Відступи між елементами. Скорочення для `row-gap` та `column-gap`.

---

## repeat()

```css
grid-template-columns: repeat(3, 1fr);
```

Повторює значення N разів.

---

## minmax()

```css
grid-template-columns: minmax(200px, 1fr);
```

Мінімальне та максимальне значення.

---

## auto-fill vs auto-fit

### auto-fill

```css
grid-template-columns: repeat(auto-fill, 200px);
```

Створює стільки колонок, скільки помістяться.

### auto-fit

```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

Як auto-fill, але повертає контент.

---

## Практичний приклад (адаптивна сітка)

```css
.container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}
```

---

## Розміщення елементів

### По лініях

```css
.item {
    grid-column: 1 / 3;
    grid-row: 1 / 2;
}
```

### span

```css
.item {
    grid-column: span 2;
}
```

Займає 2 колонки.

---

## grid-template-areas

```css
.container {
    grid-template-areas:
        "header header"
        "sidebar content"
        "footer footer";
}
```

```css
.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.content { grid-area: content; }
.footer { grid-area: footer; }
```

---

## align-items / justify-items

```css
.container {
    align-items: center;    /* вертикально */
    justify-items: center;  /* горизонтально */
}
```

Вирівнює окремі елементи всередині cell.

---

## align-content / justify-content

```css
.container {
    align-content: center;    /* вертикально */
    justify-content: center;  /* горизонтально */
}
```

Різниця:

* items — елементи всередині cell
* content — вся сітка

---

## place-items (скорочення)

```css
place-items: center;
```

Комбінує `align-items` та `justify-items`.

---

## place-content

```css
place-content: center;
```

Комбінує `align-content` та `justify-content`.

---

## Auto placement

```css
.container {
    grid-auto-flow: row;
}
```

Варіанти:

```css
row      /* автоматичне розміщення за рядками */
column   /* за колонками */
dense    /* заповнює пусті клітинки */
```

---

## Grid vs Flex

| Grid | Flex |
|------|------|
| 2D | 1D |
| розкладка-спочатку | контент-спочатку |
| складні розкладки | прості розкладки |
| елементи в двох напрямках | елементи в одному напрямку |

---

## Реальні випадки

### 1. Розкладка сторінки

```css
.container {
    display: grid;
    grid-template-columns: 250px 1fr;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header header"
        "sidebar main"
        "footer footer";
    min-height: 100vh;
}
```

### 2. Галерея

```css
.container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 15px;
}
```

### 3. Панель управління (Dashboard)

```css
.container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
}
```

---

## Часті питання на співбесіді

* Grid vs Flex — в чому різниця?
* Що таке `fr`?
* `auto-fit` vs `auto-fill` — коли використовувати?
* Як працює `grid-area`?
* Як зробити адаптивну сітку?
* Яка різниця між `items` та `content`?

---

## Частові помилки

* не розуміють grid lines та нумерацію
* плутають items та content
* не використовують minmax для адаптивності
* надмірно ускладнюють розкладки
* забувають про gap

---

## Best Practices

* використовуй Grid для макета сторінки
* комбінуй Grid з Flexbox
* використовуй `repeat()` та `minmax()`
* пиши читабельні grid-areas
* тестуй адаптивність на різних екранах
* не забувай про fallback для старих браузерів

---

## Висновок

Grid:

* найпотужніший інструмент для розкладки
* дозволяє будувати складні UI без хаку
* обов'язкове знання для сучасного frontend-розробника
* покращує якість коду та його читабельність

---

