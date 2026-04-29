# Web Accessibility (a11y)

## Визначення

**Accessibility (a11y)** — це підхід до розробки, який забезпечує можливість користування вебсайтом для всіх людей, включаючи користувачів з інвалідністю.

---

## Мета

* зробити сайт доступним для всіх
* забезпечити зручну навігацію
* відповідати стандартам (WCAG)

---

## Кому це потрібно

* користувачі з порушенням зору
* користувачі з порушенням слуху
* користувачі з моторними обмеженнями
* користувачі з когнітивними труднощами

---

## Основні принципи (WCAG)

### 1. Perceivable (сприйнятність)

Контент має бути доступний для сприйняття

### 2. Operable (керованість)

Інтерфейс має бути керований

### 3. Understandable (зрозумілість)

Контент і UI мають бути зрозумілими

### 4. Robust (надійність)

Сумісність з різними пристроями і технологіями

---

## Семантичний HTML

✅ Використовувати:

```html
<header>
<nav>
<main>
<section>
<article>
<footer>
```

❌ Уникати:

```html
<div class="header"></div>
```

Семантика = краща доступність

---

## Alt для зображень

```html
<img src="img.jpg" alt="Description">
```

Правила:

* описувати зміст
* не писати "image"
* якщо декоративне → `alt=""`

---

## Клавіатурна навігація

Користувачі повинні мати можливість:

* використовувати Tab
* переходити між елементами
* взаємодіяти без миші

---

### tabindex

```html
<button tabindex="0"></button>
```

Значення:

* `0` — стандартний порядок
* `-1` — не доступний через Tab

---

## Focus

```css
button:focus {
    outline: 2px solid blue;
}
```

Не видаляти outline без заміни

---

## ARIA (Accessible Rich Internet Applications)

Допомагає screen readers

---

### aria-label

```html
<button aria-label="Close"></button>
```

---

### aria-hidden

```html
<div aria-hidden="true"></div>
```

---

### aria-expanded

```html
<button aria-expanded="false"></button>
```

---

### role

```html
<div role="button"></div>
```

Краще:

```html
<button></button>
```

---

## Форми і доступність

---

### label

```html
<label for="email">Email</label>
<input id="email">
```

---

### aria-describedby

```html
<input aria-describedby="error">
<div id="error">Error message</div>
```

---

### aria-invalid

```html
<input aria-invalid="true">
```

---

## Контраст

Важливо:

* текст має бути читабельним
* достатній контраст кольорів

---

## Заголовки (h1-h6)

```html
<h1>Main</h1>
<h2>Section</h2>
```

Правила:

* логічна ієрархія
* не пропускати рівні

---

## Landmarks (орієнтири)

```html
<header>
<nav>
<main>
<footer>
```

Допомагають навігації

---

## Screen Readers

Інструменти, які:

* читають сторінку
* орієнтуються по DOM

---

## Hidden контент

```html
<div hidden></div>
```

або:

```html
<div aria-hidden="true"></div>
```

---

## Часті питання на співбесіді

* Що таке accessibility?
* Що таке ARIA?
* Коли використовувати aria-label?
* Чому важливий alt?
* Що таке tabindex?
* Як зробити сайт доступним?

---

## Часті помилки

* відсутній alt
* кнопки через div
* відсутній focus
* поганий контраст
* неправильні ARIA ролі

---

## Best Practices

* використовувати semantic HTML
* додавати alt
* підтримувати keyboard navigation
* використовувати ARIA лише коли потрібно
* перевіряти контраст
* тестувати зі screen reader

---

## Висновок

Accessibility:

* робить сайт доступним для всіх
* покращує UX
* часто є вимогою стандартів
* базується на семантиці, структурі і правильному HTML

---
