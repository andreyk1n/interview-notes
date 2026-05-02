# CSS `background`

## Визначення

Властивість **`background`** керує **фоном елемента**.

Включає:

* колір
* зображення
* позицію
* повторення
* розмір
* поведінку

---

## Shorthand

```css
.element {
    background: #fff url("img.jpg") no-repeat center / cover;
}
```

Скорочена форма для всіх background-властивостей

---

## Основні властивості

---

## background-color

```css
background-color: #f5f5f5;
```

Встановлює колір фону елемента. Це базовий колір, який видно, якщо немає зображення або воно прозоре.

**Можливі значення:**
* Назва кольору: `red`, `blue`
* Hex: `#f5f5f5`
* RGB: `rgb(255, 255, 255)`
* RGBA: `rgba(255, 255, 255, 0.5)` — із прозорістю
* `transparent` — прозорий

---

## background-image

```css
background-image: url("bg.jpg");
```

Встановлює зображення як фон елемента. Зображення накладається над `background-color`.

**Можливі значення:**
* `url("path/to/image.jpg")`
* `linear-gradient()` — лінійний градієнт
* `radial-gradient()` — радіальний градієнт
* `none` — без зображення

---

### Кілька фонів

```css
background-image: url("top.png"), url("bottom.png");
```

Дозволяє накласти кілька зображень одне на одне. Перший в списку буде зверху.

---

## background-repeat

```css
background-repeat: no-repeat;
```

Контролює, як повторюється фонове зображення на елементі.

| Значення  | Що робить                     |
| --------- | ----------------------------- |
| `repeat`  | Повторює по X та Y (default)  |
| `no-repeat` | Не повторює, одне зображення |
| `repeat-x` | Повторює тільки по горизоналі |
| `repeat-y` | Повторює тільки по вертикалі  |
| `space`   | Рівномірно розподіляє з проміжками |
| `round`   | Адаптивно повторює без щілин  |

---

## background-position

```css
background-position: center;
```

Встановлює позицію фонового зображення всередині елемента.

**Варіанти:**
* `top left` / `top center` / `top right` — вгорі
* `center left` / `center` / `center right` — в центрі
* `bottom left` / `bottom center` / `bottom right` — внизу
* `50% 50%` — в центрі (координати)
* `10px 20px` — вручну в пікселях від верхнього лівого кута

---

## background-size

```css
background-size: cover;
```

Контролює розмір фонового зображення.

| Значення      | Що робить                              |
| ------------- | -------------------------------------- |
| `cover`       | Заповнює весь елемент, може обрізатися |
| `contain`     | Вміщається всередину без обрізання      |
| `auto`        | Оригінальний розмір зображення (default) |
| `100px 200px` | Вручну: ширина 100px, висота 200px      |
| `50%`         | 50% від розміру елемента                |

---

## background-attachment

```css
background-attachment: fixed;
```

Визначає, як фон поводиться при прокручуванні сторінки.

| Значення | Що робить                                    |
| -------- | -------------------------------------------- |
| `scroll` | Рухається разом з елементом (default)        |
| `fixed`  | Залишається нерухомим відносно viewport      |
| `local`  | Рухається разом з контентом всередину елемента |

---

## background-origin

```css
background-origin: padding-box;
```

Визначає, звідки починається фонове зображення (точка відліку).

| Значення     | Що робить                     |
| ------------ | ----------------------------- |
| `padding-box` | З padding області (default)   |
| `border-box` | З border області              |
| `content-box` | З content області             |

---

## background-clip

```css
background-clip: border-box;
```

Визначає, в якій області видно фон (де він обрізається).

**Значення:**
```css
border-box      /* до бордера */
padding-box     /* до padding */
content-box     /* тільки контент */
text            /* тільки текст (спеціальний ефект) */
```

---

### Трюк: градієнтний текст

```css
.text {
    background: linear-gradient(red, blue);
    -webkit-background-clip: text;
    color: transparent;
}
```

Фон видно тільки на тексті, створюючи ефект кольорового тексту.

---

## Multiple backgrounds (важливо)

```css
background:
    url("top.png") no-repeat center,
    url("bg.png") repeat;
```

Дозволяє накласти кілька фонових шарів. Перший шар — зверху, останній — знизу.

---

## Background + градієнти

```css
background: linear-gradient(to right, red, blue);
```

Градієнти можна використовувати як фонове зображення, створюючи плавні переходи між кольорами.

**Типи:**
* `linear-gradient()` — прямої лінії
* `radial-gradient()` — від центру
* `conic-gradient()` — від кута

---

### Комбінація

```css
background:
    linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
    url("bg.jpg");
```

Градієнт-темна маска накладається на фонове зображення (overlay-ефект).

---

## Порядок в shorthand

```css
background:
  color
  image
  position / size
  repeat
  attachment
  origin
  clip;
```

Коли використовуєте shorthand, дотримуйтесь цього порядку для коректної роботи.

---

## Практичні приклади

---

### Hero section

```css
.hero {
    background: url("hero.jpg") center / cover no-repeat;
}
```

Великий фоновий блок, що заповнює весь екран.

---

### Overlay

```css
.overlay {
    background:
        linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
        url("bg.jpg");
}
```

Затемнення поверх зображення для кращої читабельності тексту.

---

### Pattern

```css
.pattern {
    background: url("pattern.png") repeat;
}
```

Повторюваний паттерн як фон.

---

### Fixed background

```css
.parallax {
    background-attachment: fixed;
}
```

Паралакс-ефект — фон залишається нерухомим при прокручуванні.

---

## Часті питання на співбесіді

* різниця cover vs contain?
* як працюють multiple backgrounds?
* що таке background-clip?
* як зробити overlay?
* як працює shorthand?

---

## Часті помилки

* неправильний порядок shorthand
* забувають no-repeat
* не розуміють stacking background
* проблеми з mobile + fixed

---

## Performance

* використовувати оптимізовані зображення
* уникати великих background images
* lazy loading через HTML (краще ніж CSS)

---

## Best Practices

* використовувати shorthand
* використовувати cover для hero
* комбінувати з градієнтами
* не зловживати fixed

---

## Висновок

`background`:

* потужний інструмент для UI
* підтримує кілька шарів
* критичний для дизайну

---
