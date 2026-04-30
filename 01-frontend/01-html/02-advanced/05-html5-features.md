# Особливості HTML5

## Визначення

**HTML5** — це сучасна версія HTML, яка запровадила:

* Нові семантичні елементи
* Нові API
* Покращену мультимедійну підтримку
* Вбудовані можливості для веб-застосунків

---

## Ключові інновації HTML5

* Спрощений синтаксис
* Нові теги
* Нові атрибути
* Нові веб-API
* Покращена інтеграція JavaScript

---

## 1. Спрощений DOCTYPE

```html
<!DOCTYPE html>
```

Раніше був набагато складніший синтаксис.

---

## 2. Семантичні елементи

```html
<header>
<nav>
<main>
<section>
<article>
<aside>
<footer>
```

Переваги:

* Поліпшення SEO
* Краща доступність
* Підвищена читабельність

---

## 3. Нові мультимедійні елементи

### Відео

```html
<video controls>
    <source src="video.mp4" type="video/mp4">
</video>
```

### Аудіо

```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
</audio>
```

Раніше потребував плагіну Flash.

---

## 4. Нові елементи форми

### Нові типи input

```html
<input type="email">
<input type="date">
<input type="range">
<input type="color">
```

Вбудована валідація включена.

### Нові атрибути

```html
<input required>
<input placeholder="Ім'я">
<input autofocus>
```

---

## 5. Canvas API

```html
<canvas id="canvas"></canvas>
```

```js
const ctx = canvas.getContext('2d')
ctx.fillRect(10, 10, 100, 100)
```

Малювання графіки через JavaScript.

---

## 6. Підтримка SVG

```html
<svg width="100" height="100">
    <circle cx="50" cy="50" r="40" />
</svg>
```

Підтримка векторної графіки.

---

## 7. Веб-сховище

### localStorage

```js
localStorage.setItem('key', 'value')
```

### sessionStorage

```js
sessionStorage.setItem('key', 'value')
```

Альтернатива cookies.

---

## 8. Geolocation API

```js
navigator.geolocation.getCurrentPosition()
```

Отримання геолокації користувача.

---

## 9. Drag and Drop API

```html
<div draggable="true"></div>
```

---

## 10. Web Workers

```js
const worker = new Worker('worker.js')
```

Фонові процеси.

---

## 11. History API

```js
history.pushState({}, '', '/page')
```

Навігація SPA.

---

## 12. Офлайн (Application Cache)

Застаріло. Замінено Service Workers.

---

## 13. Семантичний HTML + API = Веб-застосунки

HTML5 дозволив:

* Створення Single Page Applications
* Роботу без плагінів
* Використання браузера як платформи

---

## Поширені питання на співбесідах

* Що таке HTML5?
* Які нові теги були запроваджені?
* Що таке Canvas?
* localStorage проти cookies?
* Що такі Web Workers?
* Що таке семантичний HTML?

---

## Поширені помилки

* Використання застарілих технологій (Flash)
* Неправильне використання нових типів input
* Ігнорування браузерних API
* Плутанина між сховищем і cookies

---

## Найкращі практики

* Використовувати семантичний HTML
* Використовувати нові типи input
* Оптимізувати веб-API
* Уникати застарілих рішень
* Комбінувати HTML5 з JavaScript

---

## Висновок

HTML5:

* Зробив веб сучасним
* Додав API і можливості
* Дозволив створювати повнофункціональні веб-застосунки

---
