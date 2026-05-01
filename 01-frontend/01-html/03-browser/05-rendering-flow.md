# Rendering flow (Потік рендерингу браузера)

## Визначення

Rendering flow — це процес, за яким браузер перетворює HTML, CSS і JavaScript у пікселі на екрані.

Іншими словами:
як код стає UI

---

## Загальна схема

```id="flow1"
HTML → DOM
CSS → CSSOM
DOM + CSSOM → Render Tree
Render Tree → Layout
Layout → Paint
Paint → Composite
```

---

## 1. Завантаження ресурсів

Браузер:

* завантажує HTML
* паралельно завантажує CSS, JS, images

Важливо:

* CSS блокує рендер
* JS може блокувати парсинг

---

## 2. Парсинг HTML → DOM

```html id="ex1"
<div><p>Hello</p></div>
```

Створюється DOM:

```id="domtree"
div
 └── p
    └── "Hello"
```

DOM — дерево об'єктів

---

## 3. Парсинг CSS → CSSOM

```css id="css1"
p { color: red; }
```

Створюється CSSOM:

```id="cssom"
p → color: red
```

CSSOM — правила стилів

---

## 4. Render Tree

DOM + CSSOM = Render Tree

Включає:

* тільки видимі елементи
* без display: none

---

## 5. Layout (Reflow)

Браузер обчислює:

* позиції
* розміри
* відступи

Визначає де що знаходиться

---

## 6. Paint

Браузер:

* малює кольори
* текст
* тіні
* бордери

Визначає як виглядає

---

## 7. Composite

Останній етап:

* збір шарів
* відображення на екрані

GPU оптимізація

---

## Візуалізація процесу

```id="flow2"
DOM → CSSOM
     ↓
  Render Tree
     ↓
    Layout
     ↓
    Paint
     ↓
  Composite
```

---

## Blocking ресурси

---

### CSS (Render Blocking)

* блокує render tree
* браузер чекає стилі

---

### JS (Parser Blocking)

```html id="js1"
<script src="app.js"></script>
```

Блокує парсинг HTML

---

### defer

```html id="js2"
<script src="app.js" defer></script>
```

Виконується після HTML

---

### async

```html id="js3"
<script src="app.js" async></script>
```

Виконується одразу після завантаження

---

## Reflow vs Repaint

---

### Reflow (Layout)

Причини:

* зміна розмірів
* додавання елементів
* зміна шрифтів

Дорогий процес

---

### Repaint

Причини:

* зміна кольору
* visibility

Дешевший

---

## Що викликає reflow

```js
element.style.width = '100px'
element.style.margin = '10px'
```

---

## Оптимізація

---

### Мінімізувати DOM зміни

❌

```js
for (...) {
  document.body.appendChild(el)
}
```

✅

```js
const fragment = document.createDocumentFragment()
```

---

### Batch updates

* групувати зміни

---

### Використовувати transform

```css id="perf1"
transform: translateX(100px);
```

Не викликає reflow

---

## Critical Rendering Path

Найважливіший шлях:

* мінімізувати ресурси
* оптимізувати завантаження

---

## GPU vs CPU

* Layout → CPU
* Paint → CPU
* Composite → GPU

---

## Часті питання на співбесіді

* як браузер рендерить сторінку?
* DOM vs CSSOM?
* що таке render tree?
* reflow vs repaint?
* що блокує рендер?
* defer vs async?

---

## Часті помилки

* великі DOM зміни
* blocking JS
* не оптимізований CSS
* зайві reflow

---

## Best Practices

* використовувати defer
* мінімізувати reflow
* оптимізувати CSS
* використовувати transform
* кешувати DOM

---

## Висновок

Rendering Flow:

* основа роботи браузера
* впливає на performance
* критично важливий для frontend

---

