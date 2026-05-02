# CSS `width` / `height`

## Визначення

**`width` і `height`** — це властивості, які визначають **ширину та висоту елемента**.

Вони контролюють:

* розмір контенту
* поведінку layout
* адаптивність

---

## Базовий синтаксис

```css
.box {
    width: 200px;
    height: 100px;
}
```

---

## Як працює за замовчуванням

---

### Block елементи

```css
div {
    width: auto;
}
```

* займають всю ширину контейнера
* height залежить від контенту

---

### Inline елементи

```css
span {
}
```

* width/height НЕ працюють
* розмір = контент

---

## Одиниці вимірювання

---

### Абсолютні

```css
width: 200px;
```

Фіксована величина, незалежна від батька чи viewport

---

### Відносні

```css
width: 50%;
```

Відсоток від ширини батька. Змінюється зі зміною батька

---

### Viewport

```css
width: 100vw;
height: 100vh;
```

Залежать від розміру екрану. 100vw — ширина екрану, 100vh — висота екрану

---

### Rem / Em

```css
width: 20rem;
```

Відносні одиниці. rem залежить від font-size батька, em від font-size елемента

---

## auto

```css
width: auto;
height: auto;
```

* width — залежить від display (для block займає 100%, для inline від контенту)
* height — обчислюється від контенту

---

## max-width / min-width

---

### max-width

```css
img {
    max-width: 100%;
}
```

Встановлює максимальну ширину. Елемент не може бути ширше за цю величину

---

### min-width

```css
.box {
    min-width: 200px;
}
```

Встановлює мінімальну ширину. Елемент не може бути вужче за цю величину

---

## max-height / min-height

```css
.box {
    min-height: 100px;
}
```

Аналогічно до max-width / min-width, але для висоти

---

## width vs max-width

---

### Проблема з width

```css
.container {
    width: 1200px;
}
```

Завжди точна ширина. На менших екранах викликає overflow

---

### Правильно з max-width

```css
.container {
    max-width: 1200px;
    margin: 0 auto;
}
```

Максимальна ширина 1200px, але на менших екранах займає 100% контейнера

---

## Box-sizing вплив

---

### content-box (default)

```css
width = content only
```

Width визначає тільки розмір контенту. Padding і border додаються до загального розміру

---

### border-box

```css
width = content + padding + border
```

Width включає контент, padding та border. Простіше розраховувати розміри

---

## aspect-ratio

```css
.box {
    aspect-ratio: 16 / 9;
}
```

Встановлює співвідношення сторін. При зміні width автоматично обчислюється height

---

## width: 100%

```css
.box {
    width: 100%;
}
```

* займає всю ширину батька
* може викликати overflow з padding

---

## height: 100%

```css
.box {
    height: 100%;
}
```

працює тільки якщо:

* у батька явно встановлена height

---

## overflow + height

```css
.box {
    height: 100px;
    overflow: auto;
}
```

Коли контент перевищує встановлену висоту, з'являється скроллбар

---

## Intrinsic sizing

---

### fit-content

```css
width: fit-content;
```

Ширина рівна контенту, але не більше за контейнер

---

### min-content

```css
width: min-content;
```

Мінімальна ширина для оптимального вмісту (враховує перерви в тексту)

---

### max-content

```css
width: max-content;
```

Максимально можлива ширина контенту без переносів

---

## Flex/Grid нюанси

---

### flex

```css
.item {
    flex: 1;
}
```

У flex контейнерах width може ігноруватись на користь flex-basis

---

### min-width: 0

```css
.item {
    min-width: 0;
}
```

Необхідна у flex для того, щоб контент не переповнював контейнер

---

## Практичні приклади

---

### Container

```css
.container {
    max-width: 1200px;
    margin: 0 auto;
}
```

---

### Responsive image

```css
img {
    max-width: 100%;
    height: auto;
}
```

---

### Full screen

```css
.hero {
    height: 100vh;
}
```

---

### Card

```css
.card {
    width: 300px;
}
```

---

## Часті питання на співбесіді

* width vs max-width та коли використовувати кожну?
* чому height: 100% не працює без height у батька?
* що робить box-sizing та його різниця?
* що таке aspect-ratio та як його застосовувати?
* різниця між min-content та max-content?

---

## Часті помилки

* width замість max-width для контейнерів
* overflow через padding з width: 100%
* height: 100% без встановленої height у батька
* ігнорування box-sizing при розрахунках

---

## Best Practices

* використовувати max-width для контейнерів
* віддавати перевагу відносним одиницям (%, rem)
* уникати фіксованих height, використовувати min-height
* застосовувати aspect-ratio для медіа елементів

---

## Висновок

`width/height`:

* основа для layout системи
* сильно залежать від контексту (display, box-sizing, батько)
* критичні для responsive дизайну

---

