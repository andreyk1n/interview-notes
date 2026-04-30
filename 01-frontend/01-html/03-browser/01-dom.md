# DOM (Document Object Model)

## Визначення

**DOM (Document Object Model)** — це об’єктна модель HTML-документа, яка представляє сторінку у вигляді дерева об’єктів, з яким можна взаємодіяти через JavaScript.

Кожен HTML елемент = DOM node (вузол)

---

## Як працює DOM

HTML:

```html id="p2a3df"
<body>
    <div>
        <p>Hello</p>
    </div>
</body>
```

DOM:

```
body
 └── div
            └── p
                     └── "Hello"
```

Це дерево називається DOM tree

---

## Типи вузлів (Nodes)

### 1. Element Node

```html id="v1m2pz"
<div></div>
```

---

### 2. Text Node

```html id="p8f7qw"
<p>Hello</p>
```

---

### 3. Attribute Node (концептуально)

```html id="d9l2ka"
<div id="app"></div>
```

---

### 4. Document Node

```js id="x8c2sl"
document
```

---

## DOM vs HTML

| HTML      | DOM                 |
| --------- | ------------------- |
| текст     | об’єкти             |
| статичний | динамічний          |
| файл      | структура в пам’яті |

---

## Доступ до DOM

---

### Старі методи

```js id="5j7t2m"
document.getElementById('id')
document.getElementsByClassName('class')
document.getElementsByTagName('div')
```

---

### Сучасні методи

```js id="r9x2yt"
document.querySelector('.class')
document.querySelectorAll('div')
```

Працюють як CSS селектори

---

## Навігація по DOM

```js id="a7m1lp"
element.parentNode
element.children
element.firstChild
element.lastChild
element.nextSibling
element.previousSibling
```

---

## Зміна DOM

---

### Зміна тексту

```js id="n4t9xp"
element.textContent = "Hello"
element.innerText = "Hello"
```

---

### HTML

```js id="d5r8yt"
element.innerHTML = "<span>Hi</span>"
```

---

### Атрибути

```js id="q7v2sa"
element.setAttribute('id', 'test')
element.getAttribute('id')
```

---

### Класи

```js id="m6c3kd"
element.classList.add('active')
element.classList.remove('active')
element.classList.toggle('active')
```

---

### Стилі

```js id="t2w9fn"
element.style.color = 'red'
```

---

## Створення елементів

```js id="p0z8vn"
const div = document.createElement('div')
div.textContent = 'Hello'
document.body.appendChild(div)
```

---

## Видалення

```js id="b3k7qy"
element.remove()
```

---

## Події (Events)

```js id="m2t4qf"
button.addEventListener('click', () => {
    console.log('clicked')
})
```

---

## Event propagation

* bubbling ↑
* capturing ↓

```js id="q1r8we"
event.stopPropagation()
```

---

## Reflow & Repaint

### Reflow (layout)

* змінює розміри/позицію

### Repaint

* змінює вигляд (колір)

Впливає на performance

---

## Virtual DOM (React)

* копія DOM в пам’яті
* оптимізує оновлення

---

## Часті питання на співбесіді

* Що таке DOM?
* DOM vs HTML?
* querySelector vs getElementById?
* innerHTML vs textContent?
* що таке event bubbling?
* що таке reflow?

---

## Часті помилки

* використання innerHTML без потреби
* часті зміни DOM (performance)
* неправильна робота з подіями
* ігнорування delegation

---

## Best Practices

* використовувати querySelector
* мінімізувати маніпуляції DOM
* використовувати event delegation
* не зловживати innerHTML
* кешувати селектори

---

## Висновок

DOM:

* дозволяє керувати HTML через JS
* є основою фронтенд-розробки
* впливає на performance і UX

---

