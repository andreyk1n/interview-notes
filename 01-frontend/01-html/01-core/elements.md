# HTML Elements

## Визначення

**HTML element** — це базова структурна одиниця HTML-документа, яка складається з:

* відкриваючого тегу
* контенту
* закриваючого тегу (якщо не void)

```html
<tagname>content</tagname>
```

Приклад:

```html
<p>Hello World</p>
```

---

## Структура елемента

```html
<a href="https://example.com">Link</a>
```

Складається з:

* `<a>` — відкриваючий тег
* `href` — атрибут
* `Link` — контент
* `</a>` — закриваючий тег

---

## Типи HTML елементів

### 1. Container (парні)

Мають відкриваючий і закриваючий тег.

```html
<div>Content</div>
<p>Text</p>
<section>Section</section>
```

---

### 2. Void elements (самозакриваючі)

Не мають закриваючого тегу.

```html
<img src="image.jpg">
<input type="text">
<br>
<hr>
<meta>
<link>
```

Особливості:

* не містять контенту
* у HTML5 не потребують `/`

---

## Block vs Inline

### Block-level elements

**Характеристики:**

* займають всю доступну ширину
* починаються з нового рядка
* можуть містити інші block і inline елементи

**Приклади:**

```html
div
p
section
article
header
footer
```

---

### Inline elements

**Характеристики:**

* займають тільки ширину контенту
* не переносять рядок
* зазвичай містять текст або інші inline елементи

**Приклади:**

```html
span
a
strong
em
img
```

---

### Вкладеність

Неправильно:

```html
<span>
  <div></div>
</span>
```

Правильно:

```html
<div>
  <span></span>
</div>
```

---

## Семантичні елементи

Семантичні елементи описують значення контенту.

### Несемантичні:

```html
<div class="header"></div>
<div class="nav"></div>
```

### Семантичні:

```html
<header></header>
<nav></nav>
<main></main>
<section></section>
<article></article>
<aside></aside>
<footer></footer>
```

---

### Переваги семантики

* покращує SEO
* допомагає screen readers
* робить код зрозумілішим
* покращує структуру документа

---

## Основні категорії елементів

### Контейнери

```html
div — універсальний блок
span — універсальний inline
```

---

### Текстові

```html
h1-h6 — заголовки
p — параграф
strong — важливість
em — наголос
small — менш важливий текст
```

---

### Посилання

```html
<a href="https://example.com">Link</a>
```

**Атрибути:**

* `href`
* `target`
* `rel`

---

### Медіа

```html
<img src="img.jpg" alt="description">
video
audio
```

Важливо:

* `alt` — accessibility + SEO

---

### Списки

```html
<ul> — маркований
<ol> — нумерований
<li> — елемент списку
```

---

### Таблиці

```html
<table>
  <thead>
  <tbody>
  <tr>
  <td>
</table>
```

---

### Форми

```html
<form>
  <input>
  <textarea>
  <select>
  <button>
</form>
```

---

## Атрибути

Атрибути додають додаткову інформацію елементу.

```html
<input type="text" disabled>
```

---

### Глобальні атрибути

```html
id
class
style
title
hidden
data-*
```

---

### Boolean атрибути

```html
disabled
checked
required
readonly
```

Особливість:

```html
<input disabled>
```

(значення не потрібне)

---

## Nesting (вкладеність)

Правильна структура:

```html
<div>
  <p>
    <span>Text</span>
  </p>
</div>
```

Правило:

* елементи повинні правильно закриватися
* не можна перетинати теги

Неправильно:

```html
<p><span></p></span>
```

---

## DOM (зв’язок з JS)

Кожен HTML елемент стає **DOM-вузлом**.

```html
<div id="app"></div>
```

```js
document.getElementById('app')
```

---

## Часті питання на співбесіді

* Різниця між block і inline?
* Що таке semantic HTML?
* Що таке void elements?
* Чим `<div>` відрізняється від `<section>`?
* Для чого потрібен `alt`?
* Чи можна вкладати block в inline?
* Що таке DOM?

---

## Часті помилки

* відсутній `alt` у `<img>`
* використання тільки `div`
* неправильна вкладеність
* зловживання inline стилями
* ігнорування семантики

---

## Best Practices

* використовувати семантичні теги
* писати валідний HTML
* уникати зайвих обгорток
* дотримуватись правильної вкладеності
* думати про accessibility

---

