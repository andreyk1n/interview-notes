# HTML Metadata

## Визначення

**Metadata** — це дані про дані, які описують HTML-документ і не відображаються безпосередньо на сторінці, але використовуються браузерами, пошуковими системами та іншими сервісами.

Метадані розміщуються всередині тегу `<head>`.

---

## Де використовується

```html
<head>
    <!-- Metadata here -->
</head>
```

---

## Основні типи metadata

* технічні (charset, viewport)
* SEO (description, keywords)
* соціальні (Open Graph)
* браузерні (icons, theme-color)
* поведінкові (robots, refresh)

---

## Базові meta-теги

---

### Кодування

```html
<meta charset="UTF-8">
```

Визначає кодування символів
UTF-8 — стандарт

---

### Viewport (адаптивність)

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Контролює відображення на мобільних пристроях

Параметри:

* `width=device-width`
* `initial-scale=1.0`

---

### Description (SEO)

```html
<meta name="description" content="Page description">
```

Використовується в результатах пошуку

---

### Keywords (застаріло)

```html
<meta name="keywords" content="html, css, js">
```

Майже не використовується сучасними пошуковиками

---

### Author

```html
<meta name="author" content="Your Name">
```

---

## Meta robots

```html
<meta name="robots" content="index, follow">
```

Керує індексацією

Значення:

* `index / noindex`
* `follow / nofollow`

---

## Open Graph (соціальні мережі)

Використовується для прев’ю при шерінгу

```html
<meta property="og:title" content="Title">
<meta property="og:description" content="Description">
<meta property="og:image" content="image.jpg">
<meta property="og:url" content="https://example.com">
```

---

## Twitter Cards

```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Title">
<meta name="twitter:description" content="Description">
```

---

## Favicon та іконки

```html
<link rel="icon" href="/favicon.ico">
<link rel="apple-touch-icon" href="/icon.png">
```

---

## Theme color

```html
<meta name="theme-color" content="#ffffff">
```

Колір браузера на мобільних

---

## HTTP-equiv

Імітація HTTP-заголовків

```html
<meta http-equiv="refresh" content="5">
```

Перезавантаження сторінки

---

## Base URL

```html
<base href="https://example.com/">
```

Базовий шлях для всіх URL

---

## Підключення ресурсів

---

### CSS

```html
<link rel="stylesheet" href="styles.css">
```

---

### Preload

```html
<link rel="preload" href="font.woff2" as="font">
```

---

### Prefetch

```html
<link rel="prefetch" href="next-page.html">
```

---

## Charset vs Content-Type

```html
<meta charset="UTF-8">
```

старий варіант:

```html
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
```

Використовувати перший

---

## Вплив на SEO

Важливі:

* title
* description
* og tags

Менш важливі:

* keywords

---

## Вплив на Performance

* preload → швидше завантаження
* prefetch → оптимізація навігації

---

## Часті питання на співбесіді

* Що таке metadata?
* Для чого meta viewport?
* Що таке Open Graph?
* Чим preload відрізняється від prefetch?
* Що робить robots?
* Чи важливий keywords?

---

## Часті помилки

* відсутній viewport
* неправильний description
* відсутній favicon
* дубльовані meta-теги
* використання застарілих тегів

---

## Best Practices

* завжди вказувати charset
* використовувати viewport
* писати унікальний description
* додавати Open Graph
* оптимізувати ресурси (preload)

---

## Висновок

Metadata:

* не видно користувачу
* критично для SEO, performance і UX
* впливає на те, як сторінка сприймається браузером і сервісами

---

