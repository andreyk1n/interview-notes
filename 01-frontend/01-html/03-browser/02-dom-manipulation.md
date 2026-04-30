# DOM Manipulation (HTML Perspective)

## Definition

**DOM manipulation** — це зміна структури, вмісту або атрибутів HTML-документа через JavaScript.

У контексті HTML це означає:

* як HTML перетворюється в DOM
* як зміни в DOM впливають на HTML структуру

---

## Зв'язок HTML ↔ DOM

HTML:

```html
<div id="app">
    <p>Hello</p>
</div>
```

DOM:

* `div` — element node
* `p` — child node
* `Hello` — text node

Будь-яка зміна через JS змінює DOM та оновлює HTML.

---

## Основні типи маніпуляцій

### 1. Зміна контенту

#### textContent

```js
element.textContent = "New text"
```

Безпечний (не парсить HTML).

#### innerText

```js
element.innerText = "New text"
```

Враховує стилі (display, visibility).

#### innerHTML

```js
element.innerHTML = "<span>New</span>"
```

Парсить HTML. Ризик XSS.

#### Різниця

| Метод       | HTML | Безпека | Продуктивність |
| ----------- | ---- | ------- | -------------- |
| textContent | Ні   | Так     | швидкий        |
| innerText   | Ні   | Так     | повільніший    |
| innerHTML   | Так  | Ні      | середній       |

### 2. Зміна атрибутів

```js
element.setAttribute('id', 'new')
element.getAttribute('id')
element.removeAttribute('id')
```

#### Dataset

```html
<div data-user-id="123"></div>
```

```js
element.dataset.userId
```

### 3. Класи

```js
element.classList.add('active')
element.classList.remove('active')
element.classList.toggle('active')
element.classList.contains('active')
```

### 4. Стилі

```js
element.style.color = 'red'
element.style.display = 'none'
```

Inline styles (не best practice).

### 5. Створення елементів

```js
const div = document.createElement('div')
div.textContent = 'Hello'
```

### 6. Додавання в DOM

```js
parent.appendChild(child)
parent.append(child)
parent.prepend(child)
```

#### insertAdjacentHTML

```js
element.insertAdjacentHTML('beforeend', '<p>Text</p>')
```

Позиції:

* beforebegin
* afterbegin
* beforeend
* afterend

### 7. Видалення елементів

```js
element.remove()
parent.removeChild(child)
```

### 8. Заміна

```js
parent.replaceChild(newEl, oldEl)
```

---

## DocumentFragment (оптимізація)

```js
const fragment = document.createDocumentFragment()

for (let i = 0; i < 1000; i++) {
    const li = document.createElement('li')
    fragment.appendChild(li)
}

ul.appendChild(fragment)
```

Мінімізує reflow.

---

## Reflow / Repaint

**Reflow** — зміна layout.

**Repaint** — зміна стилів.

Часті маніпуляції призводять до поганої продуктивності.

---

## Event delegation

```js
parent.addEventListener('click', (e) => {
    if (e.target.matches('button')) {
        console.log('clicked')
    }
})
```

Менше слухачів — кращий performance.

---

## Live vs Static колекції

```js
document.getElementsByClassName() // live
document.querySelectorAll()       // static
```

---

## Безпека (XSS)

Небезпечно:

```js
element.innerHTML = userInput
```

Краще:

```js
element.textContent = userInput
```

---

## Часті питання на співбесіді

* innerHTML vs textContent?
* як створити елемент?
* append vs appendChild?
* що таке DocumentFragment?
* що таке event delegation?
* що таке reflow?

---

## Часті помилки

* зловживання innerHTML
* багато перерендерів
* відсутність delegation
* прямі inline стилі
* неочищені event listeners

---

## Best Practices

* використовувати textContent для тексту
* мінімізувати DOM-операції
* використовувати DocumentFragment
* застосовувати delegation
* кешувати DOM елементи

---

## Висновок

DOM manipulation дозволяє змінювати HTML динамічно, є основою роботи JS у браузері та сильно впливає на performance.

