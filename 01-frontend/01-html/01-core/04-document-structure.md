# HTML Document Structure

## Визначення

**HTML document structure** — це базова ієрархія та організація HTML-документа, яка визначає:

* як браузер читає сторінку
* як відображається контент
* як працює SEO та accessibility

---

## Базова структура HTML документа

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <!-- Content -->
</body>
</html>
```

---

## Основні частини документа

---

### `<!DOCTYPE html>`

* декларація типу документа
* повідомляє браузеру, що це HTML5

Без нього браузер може перейти в **quirks mode**

---

### `<html>`

* кореневий елемент документа
* містить весь HTML

```html
<html lang="uk"></html>
```

Атрибут `lang`:

* важливий для accessibility та SEO

---

### `<head>`

Містить **метадані**, які не відображаються на сторінці

---

#### Основні елементи в `<head>`:

```html
<meta charset="UTF-8">
```

* кодування (UTF-8 — стандарт)

---

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

* адаптивність (responsive design)

---

```html
<title>Page Title</title>
```

* назва сторінки (вкладка браузера)

---

```html
<link rel="stylesheet" href="styles.css">
```

* підключення CSS

---

```html
<script src="script.js" defer></script>
```

* підключення JS

---

### `<body>`

* містить весь видимий контент
* все, що бачить користувач

---

## Семантична структура всередині `<body>`

```html
<body>
    <header></header>
    <nav></nav>
    <main></main>
    <aside></aside>
    <footer></footer>
</body>
```

---

## Ієрархія (DOM tree)

HTML будує **дерево (DOM)**:

```html
<html>
    <body>
        <div>
            <p>Text</p>
        </div>
    </body>
</html>
```

Перетворюється в:

```
html
 └── body
            └── div
                     └── p
```

---

## Потік документа (Document Flow)

Браузер рендерить елементи:

* зверху вниз
* зліва направо

Типи потоку:

* normal flow
* positioned
* float

---

## Вкладеність (Nesting Rules)

Правильно:

```html
<div>
    <p>
        <span>Text</span>
    </p>
</div>
```

Неправильно:

```html
<p>
    <div></div>
</p>
```

---

## Head vs Body

| Head     | Body    |
| -------- | ------- |
| метадані | контент |
| не видно | видно   |
| SEO      | UI      |

---

## Важливі meta-теги

```html
<meta name="description" content="Page description">
<meta name="keywords" content="html, css">
<meta name="author" content="Name">
```

---

## Підключення ресурсів

### CSS

```html
<link rel="stylesheet" href="styles.css">
```

---

### JS

```html
<script src="app.js"></script>
```

---

### defer vs async

```html
<script src="app.js" defer></script>
<script src="app.js" async></script>
```

| Атрибут | Поведінка  |
| ------- | ---------- |
| defer   | після HTML |
| async   | одразу     |

---

## Accessibility у структурі

* `lang` у `<html>`
* правильні заголовки (`h1-h6`)
* семантичні теги

---

## SEO у структурі

* `<title>`
* `<meta description>`
* правильна ієрархія заголовків

---

## Часті питання на співбесіді

* Що таке `<!DOCTYPE>`?
* Що таке DOM?
* Різниця між `head` і `body`?
* Що робить `meta viewport`?
* defer vs async?
* Що таке document flow?

---

## Часті помилки

* відсутній DOCTYPE
* відсутній lang
* неправильний viewport
* скрипти без defer
* дубль `<h1>`

---

## Best Practices

* використовувати HTML5 DOCTYPE
* додавати lang
* писати валідну структуру
* підключати JS з defer
* використовувати семантику
* дотримуватись ієрархії заголовків

---

## Висновок

HTML document structure — це:

* основа всієї сторінки
* впливає на SEO, accessibility і performance
* визначає, як браузер читає і рендерить контент

---

