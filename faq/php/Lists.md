# Язык PHP: Массивы и списки

> [Основы](faq/php/Base) / [Математика](faq/php/Math) / [Строки и текст](faq/php/String) / [Массивы и списки](faq/php/Lists) / [Разные ошибки](faq/php/Errors) / [О сложном](faq/php/Misc)

> Работа с массивами и списками в PHP

---

- [Как создать массив?](#create-array)
- [Как сделать цикл по массиву?](#foreach)
- [Как узнать количество элементов списка или массива?](#count)
- [Как проверить, что массив пустой?](#empty)
- [Как сконвертировать массив в строку?](#to-string)

---

<a name=create-array />

## Как создать массив?
Для создания массива в php предусмотрена следующая конструкция:

```php
$array = [1, 2, 3, 4, 5, 6];
```

> Для объявления массивов используются квадратные скобки `[` и `]`.

Однако существует и старая конструкция для объявления массивов, более громоздкая и неудобная:

```php
$array = array(1, 2, 3, 4, 5, 6);
```

Вы также можете объявить именованный массив с ключами, через символ `=>`:

```php
$array = ['x' => 10, 'y' => 20, 'score' => 90];
```

Обращаться к элементам массива можно через квадратные скобки:

```php
$array = ['x' => 10, 'y' => 20];

alert($array['x']); // выведет в сообщении 10.
```

---

<a name=foreach />

## Как сделать цикл по массиву?
> Простой способ перебора всех элементов массива.

Для этого в php есть специальный цикл `foreach`, который перебирает все элементы массива, например:

```php
$array = [1, 2, 3, 4];

foreach ($array as $value) {
    alert($value);
}
```

Вы также можете перебирать массив вместе с его ключами:

```php
$array = ['x' => 10, 'y' => 20, 'z' => 30];

foreach ($array as $key => $value) {
    alert("$key = $value");
}
```

> `foreach` работает и для списков UI объектов, например для свойства `->items`.

---

<a name=count />

## Как узнать количество элементов списка или массива?

Для этого используйте функцию `count()`, это очень просто:

```php
$array = [1, 2, 3];

$result = count($array);
```

Или для компонента список:

```php
$result = count($this->listView->items);
```


---

<a name=empty />

## Как проверить, что массив пустой?

Для проверки на то что массив пустой, в php есть небольшое упрощение:

```php
$array = [];

if (!$array) {
    alert('Массив пустой');
}
```

PHP умеет сам проверять, пустой массив или нет.

> Осторожно, это не работает для списков-объектов, для них используйте `count() == 0`.

---

<a name=to-string />

## Как сконвертировать массив в строку?
> Описание функций по склейке массивов - join, implode и т.п.

Для того, чтобы сконвертировать массив в строку, есть класс `php\lib\str` и метод `join`:

```php
use php\lib\str;

$array = [1, 2, 3];

$message = str::join($array, '-');

alert($message);
```

> В сообщении будет выведено `1-2-3`.