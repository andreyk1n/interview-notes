# CSS Positioning

## Визначення

**Positioning** — це механізм у CSS, який визначає, як елемент розміщується в документі та відносно чого він позиціонується.

Контролює:
- положення елемента
- взаємодію з документним потоком
- накладання елементів

---

## Властивість `position`

---

## 1. `static` (за замовчуванням)

```css
.element {
    position: static;
}
```

Особливості:
- елемент у нормальному потоці
- властивості `top`, `left`, `right`, `bottom` не працюють

---

## 2. `relative`

```css
.element {
    position: relative;
    top: 10px;
    left: 20px;
}
```

Особливості:
- залишається в потоці
- зміщується відносно своєї початкової позиції
- займає своє місце, ніби не зміщувався

---

## 3. `absolute`

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    top: 0;
    right: 0;
}
```

Особливості:
- виходить з document flow
- позиціонується відносно:
    - найближчого предка з `position ≠ static`
    - або `body`, якщо такого немає

---

## 4. `fixed`

```css
.element {
    position: fixed;
    top: 0;
}
```

Особливості:
- відносно viewport (екрану)
- не рухається при прокручуванні
- виходить з потоку

---

## 5. `sticky`

```css
.element {
    position: sticky;
    top: 0;
}
```

Особливості:
- гібрид `relative` і `fixed`
- поводиться як relative, поки не досягне позиції
- після цього стає fixed

---

## Порівняння

| Тип      | В потоці | Відносно   | Прокрутка   |
| -------- | -------- | ---------- | ------------|
| static   | так      | —          | рухається   |
| relative | так      | себе       | рухається   |
| absolute | ні       | батька     | рухається   |
| fixed    | ні       | viewport   | не рухається|
| sticky   | так/ні   | контейнера | частково    |

---

## Координати

```css
top
right
bottom
left
```

Працюють для:
- relative
- absolute
- fixed
- sticky

---

## Z-index (накладання)

```css
.element {
    position: relative;
    z-index: 10;
}
```

Контролює:
- порядок накладання (stacking)

---

## Stacking Context

Новий контекст створюється, якщо:
- `position` + `z-index`
- `opacity < 1`
- `transform`

---

## Absolute всередині relative

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
}
```

Найчастіший патерн

---

## Центрування через absolute

```css
.child {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

---

## Sticky приклад

```css
.header {
    position: sticky;
    top: 0;
}
```

Фіксується при скролі

---

## Взаємодія з Box Model

- absolute/fixed не впливають на інших
- relative впливає
- margin працює по-різному

---

## Часті питання на співбесіді

- різниця relative vs absolute?
- як працює fixed?
- що таке sticky?
- відносно чого absolute?
- що таке z-index?

---

## Часті помилки

- відсутній `position: relative` у батька
- неправильне використання z-index
- sticky не працює через overflow
- плутанина viewport vs parent

---

## Best Practices

- використовувати flex/grid для layout
- positioning для специфічних кейсів
- завжди контролювати stacking context
- уникати складних absolute структур

---

## Висновок

Positioning:
- дозволяє точно контролювати розташування
- виходить за межі normal flow
- важливий для UI і складних компонентів
