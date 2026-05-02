# CSS Flexbox (Flexible Box Layout)

## Визначення

**Flexbox** — це одновимірна модель layout у CSS, яка дозволяє **гнучко розташовувати елементи в рядку або колонці**, контролюючи їх розміри, порядок і вирівнювання.

Основна ідея:

* контейнер керує дочірніми елементами
* елементи адаптуються до доступного простору

---

## Як мислити Flexbox

Flexbox — це не про "ставити блоки", а про:

* **розподіл простору**
* **вирівнювання**
* **адаптивність без медіа-запитів**

---

## Основні поняття

### Flex Container

```css
.container {
    display: flex;
}
```

Активує flex-контекст

---

### Flex Items

```html
<div class="container">
    <div class="item"></div>
    <div class="item"></div>
</div>
```

Тільки **прямі діти** стають flex-елементами

---

## Осі (дуже важливо!)

90% помилок = нерозуміння осей

### flex-direction: row

```text
Main axis → →
Cross axis ↓
```

### flex-direction: column

```text
Main axis ↓
Cross axis → →
```

---

## flex-direction

```css
.container {
    flex-direction: row;
}
```

Змінює ВСЮ логіку:

* justify-content → по main axis
* align-items → по cross axis

---

## justify-content (розподіл по головній осі)

```css
.container {
    justify-content: space-between;
}
```

### Візуально:

```text
flex-start:    [A B C]
center:        [  A B C  ]
flex-end:      [      A B C]
space-between: [A   B   C]
space-around:  [ A  B  C ]
space-evenly:  [ A B C ]
```

### Практичний кейс: navbar

```css
.nav {
    display: flex;
    justify-content: space-between;
}
```

---

## align-items (вирівнювання по поперечній осі)

```css
.container {
    align-items: center;
}
```

### Важливий нюанс

```css
align-items: stretch; /* default */
```

Елементи розтягуються по висоті

### baseline

```css
align-items: baseline;
```

Вирівнює по тексту, а не по коробках

---

## align-content (часто плутають!)

```css
.container {
    flex-wrap: wrap;
    align-content: space-between;
}
```

Працює ТІЛЬКИ коли:

* є кілька рядків
* є `flex-wrap`

---

## flex-wrap

```css
.container {
    flex-wrap: wrap;
}
```

### Приклад

```css
.container {
    display: flex;
    width: 300px;
}

.item {
    width: 200px;
}
```

Без wrap:

```text
[A B] (overflow)
```

З wrap:

```text
[A]
[B]
```

---

## gap (краще ніж margin)

```css
.container {
    gap: 16px;
}
```

Плюси:

* не ламає layout
* працює і по вертикалі, і по горизонталі

---

## Flex items (глибше)

### flex-grow (розширення)

```css
.item {
    flex-grow: 1;
}
```

**Приклад:**

```css
.item:nth-child(1) { flex-grow: 1; }
.item:nth-child(2) { flex-grow: 2; }
```

Результат:

```text
[ A ][    B    ]
```

B займає в 2 рази більше

---

### flex-shrink (стискання)

```css
.item {
    flex-shrink: 1;
}
```

**Приклад:**

```css
.item {
    width: 300px;
}
```

Контейнер 500px → елементи стискаються

---

### flex-basis (база)

```css
.item {
    flex-basis: 200px;
}
```

Це **стартовий розмір**, до grow/shrink

---

## flex shorthand (критично важливо)

```css
.item {
    flex: 1;
}
```

Дорівнює:

```css
flex: 1 1 0;
```

Найчастіше питання на співбесіді

### Варіанти

```css
flex: 0 0 auto; /* фікс */
flex: 1;        /* рівномірно */
flex: 2;        /* більше місця */
```

---

## order

```css
.item {
    order: 1;
}
```

**Важливо:**

* Впливає тільки на візуальний порядок
* НЕ змінює DOM

---

## align-self

```css
.item {
    align-self: flex-end;
}
```

Override контейнера

---

## Auto margins — найсильніший трюк

### Push вправо

```css
.item {
    margin-left: auto;
}
```

### Центрування

```css
.item {
    margin: auto;
}
```

Працює навіть без justify/align

---

## Практичні приклади

### 1. Центрування (найчастіше)

```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```

### 2. Sticky footer

```css
body {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

main {
    flex: 1;
}
```

### 3. Navbar + логотип + меню

```css
.nav {
    display: flex;
    align-items: center;
}

.menu {
    margin-left: auto;
}
```

### 4. Cards grid (простий)

```css
.container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.card {
    flex: 1 1 300px;
}
```

### 5. Equal height columns

```css
.container {
    display: flex;
}

.item {
    flex: 1;
}
```

### 6. Holy Grail layout

```css
.container {
    display: flex;
}

.sidebar {
    width: 200px;
}

.content {
    flex: 1;
}
```

---

## Flexbox + overflow

```css
.container {
    display: flex;
    overflow-x: auto;
}
```

Горизонтальний скрол

---

## Min-width bug (часта пастка)

```css
.item {
    min-width: 0;
}
```

Потрібно для:

* text overflow
* flex shrink

---

## Flex vs Grid (глибше)

| Flex             | Grid             |
| ---------------- | ---------------- |
| 1D               | 2D               |
| контент → layout | layout → контент |
| простий          | складний         |

---

## Часті питання на співбесіді

* Що робить `flex: 1`?
* flex-basis vs width?
* justify vs align?
* чому не працює align-content?
* як працює auto margin?
* що таке main axis?

---

## Часті помилки

* плутають осі
* не використовують gap
* не розуміють flex-basis
* забувають про wrap
* не знають про min-width: 0

---

## Best Practices

* використовувати flex для layout
* використовувати gap замість margin
* уникати складних вкладеностей
* комбінувати з grid
* думати через осі

---

## Висновок

Flexbox:

* дає контроль над простором
* спрощує адаптивність
* закриває 80% layout задач

Must-have для frontend

---

