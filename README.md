# Урок 21. ООП. Домашнее задание <br>

> **main.py** - файл запуска программы <br>

**Концепт:**

Напишите программу, обслуживающую логистику

```bash
**Доставить** 3 печеньки **из** склад **в** магазин
```

Выводить сообщение:

```bash
Курьер забирает 3 печеньки из склад
Курьер везет 3 печеньки со склад в магазин
Курьер доставил 3 печеньки в магазин

В склад хранится:

3 печеньки
2 собачки
5 коробки

В магазин хранится:

2 собачки
5 коробки
```

**Шаг 1**

Создайте абстрактный класс Storage 

**Поля:**

`items` (словарь название:количество)

`capacity` (целое число)

**Методы:**

`add`(<название>, <количество>)  - увеличивает запас items

`remove`(<название>, <количество>) - уменьшает запас items

`get_free_space()` - вернуть количество свободных мест

`get_items()` - возвращает сожержание склада в словаре {товар: количество}

`get_unique_items_count()` - возвращает количество уникальных товаров.

**Шаг 2**

Реализуйте класс Store. В нем хранится любое количество любых товаров. 

Store не может быть заполнен если свободное место закончилось

**Поля:**

items (словарь название:количество)

capacity по умолчанию равно 100

**Методы:**

add(<название>, <количество>)  - увеличивает запас items с учетом лимита capacity

remove(<название>, <количество>) - уменьшает запас items но не ниже 0

`get_free_space()` - вернуть количество свободных мест

`get_items()` - возвращает содержание склада в словаре {товар: количество}

`get_unique_items_count()` - возвращает количество уникальных товаров.

**Шаг 3**

Реализуйте класс Shop. В нем хранится **не больше 5 разных товаров**.

Shop **не может быть наполнен**, если свободное место закончилось или в нем уже есть 5 разных товаров.

**Поля:**

items (словарь название:количество)

capacity по умолчанию равно 20

**Методы:**

`add`(<название>, <количество>)  - увеличивает запас items с учетом лимита capacity

`remove`(<название>, <количество>) - уменьшает запас items но не ниже 0

`get_free_space()` - вернуть количество свободных мест

`get_items()` - возвращает содержание склада в словаре {товар: количество}

`get_unique_items_count()` - возвращает количество уникальных товаров.

**Шаг 4**

Создайте класс Request в котором будет храниться запрос

`Поля:`

from - откуда везем (строка)
to - куда везем (строка)
amount = 3,
product = "печеньки" (строка)

При инициализации  принимает список всех складов и строку типа

```bash
**Доставить** 3 печеньки **из** склад **в** магазин
```

И возвращает объект класса Request

```bash
from =  "склад",
to =  "магазин",
amount = 3,
product = "печеньки"

```

### Шаг 5

Напишите функцию main, в которой

- введите приглашение
- обрабатывайте ввод пользователя
- выполните перемещение если это возможно
- выполните перемещение

Примеры работы системы:

```bash
**Пользователь:** Курьер забирает 3 печеньки из склад

**Программа:** Нужное количество есть на складе
**Программа:** Курьер забрал 3 печеньки со склад
**Программа:** Курьер везет 3 печеньки со склад в магазин
**Программа:** Курьер доставил 3 печеньки в магазин

**Программа:** В склад хранится:

**Программа:** 3 печеньки
**Программа: 4** собачки
**Программа:** 5 коробки

**Программа:** В магазин хранится:

**Программа:** 2 собачки
**Программа:** 5 печеньки

--

**Пользователь:** Доставить 3 собачки из склад в магазин

**Программа:** Нужное количество есть на складе
**Программа:** Курьер забрал 3 собачки со склад
**Программа:** Курьер везет 3 собачки со склад в магазин
**Программа:** Курьер доставил 3 собачки в магазин

**Программа:** В склад хранится:

**Программа:** 3 печеньки
**Программа: 1** собачки
**Программа:** 5 коробки

**Программа:** В магазин хранится:

**Программа: 5** собачки
**Программа:** 5 коробки

--

**Пользователь:** Доставить 3 собачки из склад в магазин
**Программа:** Не хватает на складе, попробуйте заказать меньше

---

**Пользователь:** Доставить 3 елки из склад в магазин
**Программа:** В магазин недостаточно места, попобуйте что то другое
```