# HTML Forms

## Визначення

**HTML forms** — це механізм для збору та відправки даних користувача на сервер.

Форми використовуються для:

* авторизації
* реєстрації
* пошуку
* фільтрів
* будь-якої взаємодії з користувачем

---

## Базова структура

```html
<form action="/submit" method="POST">
    <input type="text" name="username">
    <button type="submit">Submit</button>
</form>
```

---

## Основні атрибути `<form>`

### action

URL, куди відправляються дані

```html
<form action="/api/send">
```

---

### method

```html
<form method="GET">
<form method="POST">
```

| Метод | Опис        |
| ----- | ----------- |
| GET   | дані в URL  |
| POST  | дані в body |

---

### enctype

Тип кодування даних

```html
<form enctype="multipart/form-data">
```

Використовується для:

* upload файлів

---

### autocomplete

```html
<form autocomplete="on">
```

---

### novalidate

Вимикає валідацію браузера

```html
<form novalidate>
```

---

## Основні елементи форми

---

### `<input>`

Найважливіший елемент

```html
<input type="text">
```

---

## Типи `<input>`

### Текстові

```html
<input type="text">
<input type="password">
<input type="email">
<input type="search">
<input type="tel">
<input type="url">
```

---

### Числові

```html
<input type="number">
<input type="range">
```

---

### Дата і час

```html
<input type="date">
<input type="time">
<input type="datetime-local">
```

---

### Вибір

```html
<input type="checkbox">
<input type="radio">
```

---

### Файли

```html
<input type="file">
```

---

### Кнопки

```html
<input type="submit">
<input type="reset">
<input type="button">
```

---

### Інші

```html
<input type="color">
<input type="hidden">
```

---

## Інші елементи форм

---

### `<textarea>`

```html
<textarea name="message"></textarea>
```

---

### `<select>`

```html
<select>
    <option value="1">One</option>
</select>
```

---

### `<button>`

```html
<button type="submit">Send</button>
```

---

### `<label>`

```html
<label for="email">Email</label>
<input id="email">
```

Зв’язує input з текстом

---

### `<fieldset>` і `<legend>`

```html
<fieldset>
    <legend>User Info</legend>
</fieldset>
```

---

## Атрибути input

```html
<input type="text" name="user" placeholder="Name" required>
```

---

### Основні

```html
name
value
placeholder
required
disabled
readonly
```

---

### Обмеження

```html
min
max
maxlength
pattern
```

---

## Валідація

### Вбудована (HTML)

```html
<input type="email" required>
```

---

### Типи перевірки

* required
* type (email, url)
* pattern
* min/max

---

### Вимкнення

```html
<form novalidate>
```

---

## Як відправляються дані

### GET

```
/submit?name=John&age=20
```

---

### POST

```
Body:
name=John&age=20
```

---

## name — ключовий атрибут

```html
<input name="email">
```

Без `name` дані не відправляться

---

## Accessibility

* використовувати `<label>`
* використовувати `aria-*`
* уникати placeholder як label

---

## Часті питання на співбесіді

* різниця GET vs POST?
* для чого `name`?
* що робить `required`?
* різниця input vs button?
* як працює валідація?
* що таке enctype?

---

## Часті помилки

* відсутній `name`
* відсутній label
* неправильний type
* використання placeholder замість label
* відсутня валідація

---

## Best Practices

* завжди використовувати label
* правильно обирати type
* додавати required де потрібно
* використовувати semantic структуру
* робити доступні форми

---

## Висновок

HTML Forms:

* основа взаємодії з користувачем
* дозволяють збирати і відправляти дані
* мають вбудовану валідацію
* важливі для UX і accessibility

---

