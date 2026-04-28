# HTML Form Validation

## Визначення

**HTML form validation** — це процес перевірки даних, введених користувачем у форму, перед їх відправкою на сервер.

Мета:

* запобігти некоректним даним
* покращити UX
* зменшити навантаження на сервер

---

## Типи валідації

### 1. Client-side validation (на стороні браузера)

* виконується до відправки форми
* швидка, без перезавантаження сторінки
* реалізується через HTML та JavaScript

---

### 2. Server-side validation

* виконується на сервері
* обов’язкова для безпеки
* не залежить від браузера

Важливо:
* Client-side ≠ безпека
* серверна валідація завжди потрібна

---

## Вбудована HTML валідація

Браузер автоматично перевіряє дані за допомогою атрибутів.

---

### required

```html
<input type="text" required>
```

Поле обов’язкове

---

### type

```html
<input type="email">
<input type="url">
```

Перевіряє формат

---

### minlength / maxlength

```html
<input type="text" minlength="3" maxlength="10">
```

---

### min / max

```html
<input type="number" min="1" max="100">
```

---

### pattern (regex)

```html
<input type="text" pattern="[A-Za-z]{3,}">
```

Кастомна перевірка

---

### step

```html
<input type="number" step="0.01">
```

---

## Constraint Validation API

JavaScript API для роботи з валідацією

---

### Перевірка валідності

```js
input.checkValidity()
```

---

### Повідомлення

```js
input.validationMessage
```

---

### Встановлення помилки

```js
input.setCustomValidity("Error message")
```

---

## Події валідації

```js
form.addEventListener('submit', (e) => {
    if (!form.checkValidity()) {
        e.preventDefault()
    }
})
```

---

## CSS псевдокласи

```css
input:valid {}
input:invalid {}
input:required {}
input:optional {}
```

---

## Вимкнення валідації

```html
<form novalidate>
```

---

## Кастомна валідація

```js
if (input.value.length < 3) {
    input.setCustomValidity("Too short")
} else {
    input.setCustomValidity("")
}
```

---

## Валідація email

```html
<input type="email">
```

Браузер перевіряє:

* наявність `@`
* базовий формат

---

## Валідація пароля (через pattern)

```html
<input type="password" pattern="(?=.*[A-Z])(?=.*[0-9]).{8,}">
```

Мінімум:

* 8 символів
* 1 велика літера
* 1 цифра

---

## UX при валідації

Погано:

* показувати помилки одразу
* агресивні повідомлення

Добре:

* після взаємодії
* зрозумілі тексти
* підсвітка полів

---

## Accessibility

* використовувати `<label>`
* додавати `aria-invalid`
* опис помилки через `aria-describedby`

---

## Часті питання на співбесіді

* різниця client vs server validation?
* що робить required?
* як працює pattern?
* що таке Constraint Validation API?
* як відключити валідацію?
* як зробити кастомну помилку?

---

## Часті помилки

* тільки client-side валідація
* неправильний regex
* відсутність повідомлень
* поганий UX
* ігнорування accessibility

---

## Best Practices

* завжди дублювати валідацію на сервері
* використовувати HTML validation як базу
* додавати кастомну логіку через JS
* робити зрозумілі повідомлення
* враховувати UX та accessibility

---

## Висновок

Form validation:

* забезпечує коректність даних
* покращує UX
* зменшує помилки
* повинна бути як на клієнті, так і на сервері
