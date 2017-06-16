Тестовое задание
==================================

Цель этого задания – разработать библиотеку, предоставляющую стандартные структуры данных.

```js
var Queue = require('./src/standard-library.js').Queue;

var queue = new Queue();

queue.enqueue("foo");
queue.enqueue("bar");
queue.enqueue("baz");

queue.dequeue(); // "foo"
queue.dequeue(); // "bar"
queue.dequeue(); // "baz"
```

Для этого написать реализацию функций-конструкторов, заданных в модуле `standard-library.js`.

Заготовка модуля находится в папке `src`. Тесты можно найти в папке `test`.


Общие требования
----------------

* код должен проходить валидацию `jscs`
* код должен проходить тесты
* код не должен содержать внешних библиотек
* прежде чем отправлять решение, проверьте его на соответствие [общим требованиям](https://github.com/kirillmurashov/javascript).

Как проверить свой код
----------------

```js
// Устанавливаем проверяльщик
npm install

// Проверяем
npm test

// В результате выведутся ошибки, если они есть
```

Обязательные задачи
-------------------

Необходимо реализовать следующие структуры данных.

### Коллекция (Collection)

Коллекция элементов. Поддерживает операции вставки и извлечения первого и последнего элемента, хранит ссылки на первый и последний элемент.

* first – первый элемент коллекции
* last – последний элемент коллекции
* length – количество элементов в коллекции
* isEmpty – true, если коллекция пуста
* pickFirst() – извлекает первый элемент из коллекции и возвращает его
* pickLast() – извлекает последний элемент из коллекции и возвращает его
* insertFirst() – вставляет элемент в начало колекции
* insertLast() – вставляет элемент в конец коллекции
* empty() – очищает коллекцию

### Очередь (Queue)

Список элементов, организованных по принципу "первым пришёл – первым вышел". Элементы добавляются и извлекаются с одного конца списка.

* length – количество элементов в очереди
* enqueue(item) – добавляет элемент в очередь
* dequeue() – извлекает элемент из очереди
* empty() – очищает очередь

### Массив фиксированной длины (Fixed array)

Массив фиксированного размера. Попытка добавить или получить элемент за пределами указанного диапазона должна вызывать ошибку RangeError.

* length – количество элементов в массиве
* insertAt(index, item) – записывает элемент в массив по заданному индексу
* getAt(index) – возвращает элемент по указанному индексу.

### Множество (Set)

Список, хранящий уникальные элементы.

* length - количество элементов в множестве
* insert(item) - добавляет элемент в множество
* remove(item) - удаляет элемент из множества
* has(item) - проверяет, входит ли элемент в множество
* intersect(set) – возвращает множество элементов входящих в исходное множество **и** в переданное множество (в оба сразу)
* union(set) – возвращает множество элементов входящих в исходное множество **или** в переданное множество (в любое из двух)
* empty() – очищает множество

__Встроенный объект `Set` использовать не разрешается.__

### Очередь с приоритетом PriorityQueue

Отличается от обычной очереди наличием приоритета у элементов.

* enqueue(item, priority) – кладёт элемент с priority (целое число в интервале от 1 до 100)
* dequeue() – извлекает элемент с наивысшим приоритетом из очереди. Если есть несколько элементов с одинаковым приоритетом, извлекается элемент, который был помещён в очередь первым (из элементов с наивысшим приоритетом).

### Словарь (Map)

Отличается от стандартного объекта тем, что в качестве ключей можно использовать объекты, а не только строки.

* length – количество элементов в словаре
* addItem(key, item) – добавляет элемент в словарь по указанному ключу
* removeItem(key) – извлекает элемент из словаря по указанному ключу
* getItem(key) – возвращает элемент по указанному ключу
* empty() – очищает словарь

__Встроенный объект `Map` использовать не разрешается.__
