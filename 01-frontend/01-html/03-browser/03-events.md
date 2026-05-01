# Події DOM

## Визначення

Події DOM — це сигнали (події), які генеруються браузером у відповідь на дії користувача або зміни стану сторінки.

Вони дозволяють реагувати на:

* кліки
* введення тексту
* рух миші
* завантаження сторінки
* інші взаємодії

---

## Як працюють події

```js
element.addEventListener('click', () => {
    console.log('clicked')
})
```

При кліку:

1. браузер створює подію
2. викликається обробник (handler)
3. виконується код

---

## Основні типи подій

---

### Події миші

```js
click
dblclick
mousedown
mouseup
mousemove
mouseenter
mouseleave
```

---

### Події клавіатури

```js
keydown
keyup
keypress (застарілий)
```

---

### Події форм

```js
submit
change
input
focus
blur
```

---

### Події вікна / документа

```js
load
DOMContentLoaded
resize
scroll
```

---

## Способи підписки

---

### Inline (не рекомендується)

```html
<button onclick="handleClick()"></button>
```

---

### Через властивість

```js
element.onclick = () => {}
```

Перезаписує попередній handler

---

### addEventListener (краща практика)

```js
element.addEventListener('click', handler)
```

Переваги:

* кілька handler-ів
* контроль над фазами

---

## Об'єкт події

```js
element.addEventListener('click', (event) => {
    console.log(event)
})
```

---

### Основні властивості:

```js
event.target       // елемент, де сталася подія
event.currentTarget // елемент з handler
event.type         // тип події
event.preventDefault()
event.stopPropagation()
```

---

## Поширення події

Події проходять через DOM у 2 фази:

---

### 1. Capturing (↓)

від document → до target

---

### 2. Bubbling (↑)

від target → до document

---

### Схема:

```id="m9w0qv"
document
    ↓
parent
    ↓
child (target)
    ↑
parent
    ↑
document
```

---

## Bubbling (за замовчуванням)

```js
child.addEventListener('click', () => console.log('child'))
parent.addEventListener('click', () => console.log('parent'))
```

Клік по child:

```
child
parent
```

---

## Зупинка поширення

```js
event.stopPropagation()
```

---

## preventDefault

Зупиняє стандартну поведінку

```js
form.addEventListener('submit', (e) => {
    e.preventDefault()
})
```

Приклади:

* форма не відправляється
* link не переходить

---

## Делегування подій

Один з найважливіших концептів

```js
parent.addEventListener('click', (e) => {
    if (e.target.matches('button')) {
        console.log('button clicked')
    }
})
```

Переваги:

* менше listeners
* працює для динамічних елементів

---

## once, capture, passive

```js
element.addEventListener('click', handler, {
    once: true,
    capture: false,
    passive: true
})
```

---

### once

* виконується один раз

---

### capture

* включає capturing фазу

---

### passive

* оптимізація scroll

---

## removeEventListener

```js
element.removeEventListener('click', handler)
```

Потрібна та сама функція

---

## Користувацькі події

```js
const event = new Event('my-event')
element.dispatchEvent(event)
```

---

## Події вказівника (сучасні)

```js
pointerdown
pointerup
pointermove
```

Універсальні (mouse + touch)

---

## Часті питання на співбесіді

* що таке event?
* bubbling vs capturing?
* event.target vs currentTarget?
* що робить preventDefault?
* що таке event delegation?
* addEventListener vs onclick?

---

## Часті помилки

* використання inline events
* забуті removeEventListener
* неправильне використання target
* відсутність delegation
* stopPropagation без причини

---

## Кращі практики

* використовувати addEventListener
* застосовувати delegation
* не зловживати stopPropagation
* очищати listeners
* використовувати passive для scroll

---

## Висновок

Події DOM:

* основа інтерактивності
* дозволяють реагувати на дії користувача
* важливі для performance і архітектури

---

