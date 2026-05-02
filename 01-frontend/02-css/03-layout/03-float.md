# CSS float

## Визначення

**float** — це властивість CSS, яка дозволяє елементу "плисти" ліворуч або праворуч, а інший контент (текст, inline-елементи) обтікає його.

Історично використовувався для:

* обтікання зображень
* побудови layout (до Flexbox/Grid)

---

## Основний синтаксис

```css
.element {
    float: left;
}
```

---

## Значення

| Значення | Опис |
|----------|------|
| left | елемент прилипає до лівого краю |
| right | до правого |
| none | (default) без float |
| inline-start / inline-end | залежить від напрямку тексту |

---

## Як працює float

```html
<img src="img.jpg" class="float">
<p>Text...</p>
```

```css
.float {
    float: left;
}
```

Результат:

```
[IMG] Text Text Text Text
      Text Text Text
```

Текст "обтікає" елемент

---

## Важливі особливості

### Вихід з нормального потоку

Float-елемент:

* випадає з document flow
* інші block-елементи його "не бачать"

### Висота контейнера

```html
<div class="parent">
  <div class="child"></div>
</div>
```

```css
.child {
    float: left;
}
```

`parent` → висота = 0

---

## clear (очистка float)

```css
.clear {
    clear: both;
}
```

| Значення | Опис |
|----------|------|
| left | очищає left |
| right | очищає right |
| both | очищає обидва |

### Приклад

```html
<div class="box"></div>
<div class="clear"></div>
```

---

## clearfix (класика)

```css
.parent::after {
    content: "";
    display: block;
    clear: both;
}
```

Фікс для контейнера

---

## overflow hack

```css
.parent {
    overflow: hidden;
}
```

Теж "очищає" float

---

## Float vs Inline

Float-елементи:

* поводяться як block
* але обтікаються контентом

---

## Float + display

```css
.element {
    float: left;
    display: inline; /* ігнорується */
}
```

display частково ігнорується

---

## Реальні кейси

### Обтікання картинки

```css
img {
    float: left;
    margin-right: 10px;
}
```

### Старий layout (legacy)

```css
.sidebar {
    float: left;
    width: 200px;
}

.content {
    float: right;
}
```

Зараз НЕ використовується

---

## Float vs Flex/Grid

| Float | Flex/Grid |
|-------|-----------|
| старий підхід | сучасний |
| складний | простий |
| багато багів | стабільний |

---

## Коли використовувати сьогодні

Можна:

* для обтікання текстом (image + text)

Не можна:

* для layout

---

## Часті питання на співбесіді

* що таке float?
* як працює clear?
* що таке clearfix?
* чому container collapse?
* float vs flex?

---

## Часті помилки

* не використовують clear
* container collapse
* використовують float для layout
* не розуміють flow

---

## Best Practices

* використовувати тільки для text wrap
* використовувати clearfix
* не будувати layout через float
* переходити на flex/grid

---

## Висновок

float:

* legacy інструмент
* корисний для обтікання
* замінений Flexbox і Grid для layout

---

