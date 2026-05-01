# Event Propagation (Поширення подій)

## Визначення

Event propagation — це механізм, за яким подія проходить через DOM-дерево від кореня до цільового елемента і назад.

Включає дві основні фази:

* Capturing (перехоплення)
* Bubbling (спливання)

---

## Як це працює

При кліку на елемент:

```html
<div id="parent">
    <button id="child">Click</button>
</div>
```

Подія проходить шлях:

```text
document
    ↓
html
    ↓
body
    ↓
parent
    ↓
child (target)
    ↑
parent
    ↑
body
    ↑
html
    ↑
document
```

---

## Фази propagation

### 1. Capturing phase (↓)

* подія рухається зверху вниз
* від document до target

```js
element.addEventListener('click', handler, true)
```

`true` = capturing

---

### 2. Target phase

* подія досягає цільового елемента

---

### 3. Bubbling phase (↑)

* подія піднімається вгору
* від target до document

```js
element.addEventListener('click', handler)
```

bubbling — за замовчуванням

---

## Приклад bubbling

```js
child.addEventListener('click', () => console.log('child'))
parent.addEventListener('click', () => console.log('parent'))
```

Результат:

```text
child
parent
```

---

## Приклад capturing

```js
parent.addEventListener('click', () => console.log('parent'), true)
child.addEventListener('click', () => console.log('child'))
```

Результат:

```text
parent
child
```

---

## Event Object у propagation

```js
event.target        // де сталася подія
event.currentTarget // де обробник
event.eventPhase    // фаза
```

### eventPhase значення:

| Значення | Фаза      |
| -------- | --------- |
| 1        | Capturing |
| 2        | Target    |
| 3        | Bubbling  |

---

## Зупинка propagation

### stopPropagation

```js
event.stopPropagation()
```

Зупиняє подальше поширення

---

### stopImmediatePropagation

```js
event.stopImmediatePropagation()
```

- зупиняє propagation
- зупиняє інші обробники на цьому ж елементі

---

## preventDefault (не те саме!)

```js
event.preventDefault()
```

- НЕ зупиняє propagation
- тільки скасовує стандартну дію

---

## Event Delegation

Побудований на bubbling

```js
parent.addEventListener('click', (e) => {
    if (e.target.matches('button')) {
        console.log('button clicked')
    }
})
```

Працює завдяки тому, що подія спливає вгору

---

## Коли використовувати capturing

Рідко, але:

* для глобального контролю
* для логування
* специфічні кейси UI

---

## Порядок виконання

Якщо є обробники на різних елементах:

1. capturing
2. target
3. bubbling

---

## Часті питання на співбесіді

* що таке event propagation?
* bubbling vs capturing?
* як працює stopPropagation?
* різниця між target і currentTarget?
* що таке delegation?

---

## Часті помилки

* плутанина bubbling vs capturing
* використання stopPropagation без потреби
* неправильне використання target
* ігнорування delegation

---

## Best Practices

* використовувати bubbling (за замовчуванням)
* застосовувати event delegation
* не зловживати stopPropagation
* чітко розуміти шлях події

---

## Висновок

Event propagation:

* визначає шлях події через DOM
* є основою event delegation
* критично важливий для розуміння JS подій
