# CSS `aspect-ratio`

## Визначення

**`aspect-ratio`** — це властивість, яка задає співвідношення ширини до висоти елемента.

Дозволяє:

* зберігати пропорції
* уникати "стрибків" layout (CLS)
* робити responsive блоки без хаків

---

## Базовий синтаксис

```css
.box {
    aspect-ratio: 16 / 9;
}
```

---

## Як працює

```text
width / height = ratio
```

Браузер сам рахує **відсутній параметр**

---

### Приклад

```css
.box {
    width: 320px;
    aspect-ratio: 16 / 9;
}
```

height ≈ 180px

---

```css
.box {
    height: 200px;
    aspect-ratio: 1 / 1;
}
```

width = 200px

---

## Якщо задані і width і height

```css
.box {
    width: 200px;
    height: 300px;
    aspect-ratio: 1 / 1;
}
```

`aspect-ratio` ігнорується

---

## Auto

```css
aspect-ratio: auto;
```

Значення за замовчуванням

---

## Найпоширеніші співвідношення

| Ratio | Використання |
| ----- | ------------ |
| 1/1   | квадрат |
| 16/9  | відео |
| 4/3   | фото |
| 3/2   | картки |

---

## aspect-ratio + width: 100%

```css
.box {
    width: 100%;
    aspect-ratio: 16 / 9;
}
```

Створює responsive блок, який масштабується з контейнером і зберігає задане співвідношення сторін

---

## aspect-ratio + images

```css
img {
    aspect-ratio: 16 / 9;
    object-fit: cover;
}
```

Забезпечує контроль обрізки зображення при масштабуванні

---

## aspect-ratio + object-fit

```css
img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
```

---

| Значення | Опис |
| -------- | ---------- |
| cover | заповнює контейнер, може обрізати зображення |
| contain | вміщається повністю всередину контейнера |
| fill | розтягує зображення на весь розмір контейнера |

---

## Старий підхід (padding hack)

```css
.box {
    width: 100%;
    padding-top: 56.25%;
}
```

Для співвідношення 16:9

---

Замінено на:

```css
aspect-ratio: 16 / 9;
```

---

## Flex/Grid нюанси

---

### Flex

```css
.item {
    flex: 1;
    aspect-ratio: 1 / 1;
}
```

Створює квадратні flex-елементи з рівномірним розподілом місця

---

### Grid

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.item {
    aspect-ratio: 1 / 1;
}
```

Розташовує рівні квадратні блоки в сітці

---

## Практичні приклади

---

### Відео

```css
.video {
    width: 100%;
    aspect-ratio: 16 / 9;
}
```

---

### Card image

```css
.card img {
    width: 100%;
    aspect-ratio: 4 / 3;
    object-fit: cover;
}
```

---

### Аватар

```css
.avatar {
    width: 100px;
    aspect-ratio: 1 / 1;
    border-radius: 50%;
}
```

---

### Skeleton loader

```css
.skeleton {
    aspect-ratio: 16 / 9;
    background: #eee;
}
```

---

## Accessibility + CLS

Дуже важливо використовувати для запобігання layout shift:

```css
img {
    aspect-ratio: 16 / 9;
}
```

Браузер виділяє місце для елемента заздалегідь, що запобігає стрибкам контенту при завантаженні

---

## Часті питання на співбесіді

* Що таке aspect-ratio?
* Що буде якщо задано width і height?
* Чим краще за padding hack?
* Як працює з img?

---

## Часті помилки

* задання height + aspect-ratio одночасно
* неправильне використання object-fit
* плутанина між width/height та aspect-ratio

---

## Best Practices

* використовувати для медіа-контенту
* використовувати з width: 100% для responsive дизайну
* комбінувати з object-fit для контролю масштабування
* уникати старого padding hack

---

## Висновок

`aspect-ratio`:

* сучасний спосіб контролю пропорцій елементів
* замінює застарілі хаки на основі padding
* критичний для responsive UI та запобігання CLS

