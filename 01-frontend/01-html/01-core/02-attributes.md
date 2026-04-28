# HTML Атрибути

## Визначення

**HTML атрибут** — додаткова характеристика елемента, яка встановлює його властивості, поведінку або метаданні.

Атрибути записуються **всередині відкриваючого тега**.

```html
<tagname attribute="value">вміст</tagname>
```

Приклад:

```html
<a href="https://example.com" target="_blank">Посилання</a>
```

---

## Структура атрибута

```html
name="value"
```

Складається з:

* `name` — назва атрибута
* `value` — значення атрибута (в лапках)

Лапки:

* Рекомендується використовувати `" "` або `' '`
* Без лапок можливо, але не рекомендується

---

## Типи атрибутів

### Глобальні атрибути

Доступні для **всіх HTML елементів**

#### Основні глобальні атрибути:

```html
id
class
style
title
hidden
tabindex
contenteditable
draggable
```

---

### id

Унікальний ідентифікатор елемента

```html
<div id="header"></div>
```

Характеристики:

* Повинен бути унікальним на сторінці
* Використовується в JS та CSS

---

### class

Клас(и) елемента

```html
<div class="card active"></div>
```

Характеристики:

* Множення класів дозволено
* Використовується для стилізації

---

### style

Вбудований CSS

```html
<div style="color: red;"></div>
```

Не рекомендується для великих проектів

---

### title

Підказка при наведенні

```html
<button title="Натисни мене">Кнопка</button>
```

---

### hidden

Приховує елемент

```html
<div hidden></div>
```

---

### tabindex

Контролює порядок фокусування

```html
<input tabindex="1">
```

---

### contenteditable

Робить елемент редагованим

```html
<div contenteditable="true"></div>
```

---

### draggable

Елемент можна перетягувати

```html
<div draggable="true"></div>
```

---

## Логічні атрибути

Атрибути, які не вимагають значення

```html
<input disabled>
<input checked>
<input required>
```

Спеціальний випадок:

```html
<input disabled="disabled">
```

Те саме, що й вище

---

## Специфічні атрибути

Залежать від конкретного елемента

---

### Для `<a>`

```html
<a href="https://example.com" target="_blank" rel="noopener"></a>
```

* `href` — URL
* `target` — де відкрити
* `rel` — безпека

---

### Для `<img>`

```html
<img src="img.jpg" alt="опис">
```

* `src` — шлях
* `alt` — опис

---

### Для `<input>`

```html
<input type="text" placeholder="Ім'я" required>
```

* `type`
* `placeholder`
* `value`
* `required`

---

### Для `<form>`

```html
<form action="/submit" method="POST"></form>
```

* `action`
* `method`

---

## Атрибути data-*

Користувацькі атрибути

```html
<div data-user-id="123"></div>
```

Доступ у JS:

```js
element.dataset.userId
```

---

## ARIA атрибути (доступність)

Допомагають програмам читання екрану

```html
<button aria-label="Закрити"></button>
```

### Приклади:

```html
aria-label
aria-hidden
aria-expanded
aria-role
```

---

## Атрибути подій

```html
<button onclick="handleClick()"></button>
```

Не рекомендується. Використовуйте JavaScript замість цього.

---

## Атрибути без значення проти з значенням

```html
<input disabled>        // Правильно
<input disabled="true"> // Семантично неправильно
```

---

## Вкладення та порядок

```html
<input type="text" class="input" id="name">
```

Порядок некритичний, але зазвичай:

* id → class → інші

---

## Поширені питання на собесідах

* Що такі глобальні атрибути?
* Різниця між `id` та `class`?
* Що такі логічні атрибути?
* Що таке `data-*`?
* Навіщо використовувати `alt`?
* Що робить `rel="noopener"`?
* Що таке ARIA?

---

## Поширені помилки

* Дублювання `id`
* Відсутність `alt`
* Використання вбудованого JavaScript
* Неправильне використання логічних атрибутів
* Зловживання `style`

---

## Найкращі практики

* Використовуйте `class` для стилів, `id` для логіки
* Уникайте вбудованих стилів та JavaScript
* Завжди додавайте `alt` до зображень
* Використовуйте `data-*` для користувацьких даних
* Враховуйте доступність (ARIA)

---

