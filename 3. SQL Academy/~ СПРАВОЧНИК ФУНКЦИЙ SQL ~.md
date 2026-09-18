# <font color="#92cddc">Строковые функции</font>

## <font color="#92cddc"><u>CHR</u></font>
<mark style="background:#b1ffff">Возвращает символ с указанным ASCII-кодом.</mark>
```PostgreSQL 17.5
CHR(ascii)
```

## <font color="#92cddc"><u>CONCAT</u></font>
<mark style="background:#b1ffff">Объединяет переменное количество аргументов в одну строку. Null значения игнорируются.</mark>
```PostgreSQL 17.5
CONCAT(expression [, ...])
```

## <font color="#92cddc"><u>LENGTH</u></font>
<mark style="background:#b1ffff">Возвращает количество символов в строке.</mark>
```PostgreSQL 17.5
LENGTH(string)
```

## <font color="#92cddc"><u>LOWER</u></font>
<mark style="background:#b1ffff">Преобразует строку в нижний регистр.</mark>
```PostgreSQL 17.5
LOWER(string)
```

## <font color="#92cddc"><u>LPAD</u></font>
<mark style="background:#b1ffff">Дополняет строку слева до указанной длины с помощью строки заполнителя.</mark>
```PostgreSQL 17.5
LPAD(str, len, pad_str)
```
- `str` - Строка для дополнения;
- `len` - Целевая длина;
- `pad_str` - Строка заполнителя.

***Пример:*** `SELECT LPAD('9', 5, '0')`
*Вывод:* `00009`

## <font color="#92cddc"><u>LTRIM</u></font>
<mark style="background:#b1ffff">Удаляет ведущие пробелы из строки.</mark>
```PostgreSQL 17.5
LTRIM(str)
```

## <font color="#92cddc"><u>POSITION</u></font>
<mark style="background:#b1ffff">Возвращает начальную позицию подстроки в строке или ноль, если не найдено.</mark>
```PostgreSQL 17.5
POSITION(substring IN string)
```
- `substring` - Подстрока для поиска;
- `IN string` - Исходная строка.

***Пример:*** `SELECT POSITION('om' IN 'Thomas')`
*Вывод:* `3`

## <font color="#92cddc"><u>REPEAT</u></font>
<mark style="background:#b1ffff">Повторяет строку указанное количество раз.</mark>
```PostgreSQL 17.5
REPEAT(str, count)
```
- `str` - Строка для повторения;
- `count` - Количество повторений.

## <font color="#92cddc"><u>REPLACE</u></font>
<mark style="background:#b1ffff">Заменяет все вхождения подстроки другой подстрокой в строке.</mark>
```PostgreSQL 17.5
REPLACE(string, from, to)
```
- `string` - Исходная строка;
- `from` - Подстрока для замены;
- `to` - Заменяющая подстрока.

***Пример:*** `SELECT REPLACE('abcdef', 'cd', 'XX')`
*Вывод:* `abXXef`

## <font color="#92cddc"><u>REVERSE</u></font>
<mark style="background:#b1ffff">Переворачивает строку.</mark>
```PostgreSQL 17.5
REVERSE(str)
```

## <font color="#92cddc"><u>RPAD</u></font>
<mark style="background:#b1ffff">Дополняет строку справа до указанной длины с помощью строки заполнителя.</mark>
```PostgreSQL 17.5
RPAD(str, len, pad_str)
```
- `str` - Строка для дополнения;
- `len` - Целевая длина;
- `pad_str` - Строка заполнителя.

***Пример:*** `SELECT RPAD('9', 5, '0')`
*Вывод:* `90000`

## <font color="#92cddc"><u>RTRIM</u></font>
<mark style="background:#b1ffff">Возвращает строку, у которой удалены все пробелы с правого края</mark>
```PostgreSQL 17.5
RTRIM(str)
```

## <font color="#92cddc"><u>SPLIT_PART</u></font>
<mark style="background:#b1ffff">Разделяет строку по заданному разделителю и возвращает указанную часть.</mark>
```PostgreSQL 17.5
SPLIT_PART(string, delimiter, part_number)
```
- `string` - Исходная строка;
- `delimiter` - Разеделитель для разбиения;
- `part_number` - Номер части для возврата (начиная с 1).

***Пример:*** `SELECT SPLIT_PART('a|b|c', '|', 2)`
*Вывод:* `b`

## <font color="#92cddc"><u>SUBSTRING</u></font>
<mark style="background:#b1ffff">Извлекает подстроку из строки, начиная с заданной позиции на заданную длину.</mark>
```PostgreSQL 17.5
SUBSTRING(string FROM start FOR length)
```
- `string` - Исходная строка;
- `start` - Начальная позиция (1-based);
- `length` - Количество символов для извлечения.

***Пример:***
```PostgreSQL 17.5
SELECT SUBSTRING(
		'PostgreSQL'
		FROM 1 FOR 8
	)
```
*Вывод:* `PostgreS`

## <font color="#92cddc"><u>TRIM</u></font>
<mark style="background:#b1ffff">Удаляет самую длинную строку, содержащую только указанные символы, из начала, конца или обоих концов строки.</mark>
```PostgreSQL 17.5
TRIM([LEADING | TRAILING | BOTH] [characters] FROM string)
```
- `LEADING | TRAILING | BOTH` - Откуда удалять (`BOTH` по умолч.);
- `characters` - Символы для удаления (пробел по умолчанию);
- `FROM string` - Входная строка.

***Пример:***
```PostgreSQL 17.5
SELECT TRIM(
		BOTH 'x'
		FROM 'xTomx'
	)
```
*Вывод:* `Tom`

## <font color="#92cddc"><u>UPPER</u></font>
<mark style="background:#b1ffff">Преобразует строку в верхний регистр.</mark>
```PostgreSQL 17.5
UPPER(string)
```

---
# <font color="#f79646">Числовые функции</font>

## <font color="#f79646"><u>ABS</u></font>
<mark style="background:#d4b106">Возвращает абсолютное значение числа. Абсолютное значение - расстояние от нуля до числа на координатной прямой.</mark>
```PostgreSQL 17.5
ABS(number)
```

***Пример:***
```PostgreSQL 17.5
SELECT ABS(-5.7)
```
*Вывод:* `5.7`

## <font color="#f79646"><u>CEIL</u></font>
<mark style="background:#d4b106">Возвращает наименьшее целое, большее или равное числу.</mark>
```PostgreSQL 17.5
CEIL(number)
```

***Пример:***
```sql
SELECT CEIL(5.3)
```
*Вывод:* `6`

## <font color="#f79646"><u>COS</u></font>
<mark style="background:#d4b106">Возвращает косинус угла в радианах.</mark>
```PostgreSQL 17.5
COS(angle)
```
- `angle` - Угол в радианах.

## <font color="#f79646"><u>EXP</u></font>
<mark style="background:#d4b106">Возвращает `e` в степени числа.</mark>
```PostgreSQL 17.5
EXP(num)
```

***Пример:***
```PostgreSQL 17.5
SELECT EXP(1)
```
*Вывод:* `2.718281828459045`

## <font color="#f79646"><u>FLOOR</u></font>
<mark style="background:#d4b106">Возвращает наибольшее целое, меньшее или равное числу.</mark>
```PostgreSQL 17.5
FLOOR(number)
```

***Пример:***
```PostgreSQL 17.5
SELECT FLOOR(5.7)
```
*Вывод:* `5`

## <font color="#f79646"><u>GREATEST</u></font>
<mark style="background:#d4b106">Возвращает наибольшее значение из списка значений.</mark>
```PostgreSQL 17.5
GREATEST(num [,num])
```

***Пример:***
```PostgreSQL 17.5
SELECT GREATEST(1, 2, -1)
```
*Вывод:* `2`

## <font color="#f79646"><u>LEAST</u></font>
<mark style="background:#d4b106">Возвращает наименьшее значение из списка значений.</mark>
```PostgreSQL 17.5
LEAST(num [,num])
```

***Пример:***
```PostgreSQL 17.5
SELECT LEAST(1, 2, -1)
```
*Вывод:* `-1`

## <font color="#f79646"><u>LOG</u></font>
<mark style="background:#d4b106">Возвращает логарифм числа по указанному основанию.</mark>
```PostgreSQL 17.5
LOG(base, num)
```
- `base` - Основание;
- `num` - Число.

***Пример:***
```PostgreSQL 17.5
SELECT LOG(10, 100)
```
*Вывод:* `2.0000000000000000`

## <font color="#f79646"><u>MOD</u></font>
<mark style="background:#d4b106">Возвращает остаток от деления.</mark>
```PostgreSQL 17.5
MOD(dividend, divisor)
```
- `dividend` - Дивиденд;
- `divisor` - Делитель.

***Пример:***
```PostgreSQL 17.5
SELECT MOD(7, 3)
```
*Вывод:* `1`

## <font color="#f79646"><u>PI</u></font>
<mark style="background:#d4b106">Возвращает значение пи.</mark>
```PostgreSQL 17.5
PI()
```

***Пример:***
```PostgreSQL 17.5
SELECT PI()
```
*Вывод:* `3.141592653589793`

## <font color="#f79646"><u>POWER</u></font>
<mark style="background:#d4b106">Возвращает число, возведенное в степень.</mark>
```PostgreSQL 17.5
POWER(num, power)
```

***Пример:***
```PostgreSQL 17.5
SELECT POWER(2, 2)
```
*Вывод:* `4`

## <font color="#f79646"><u>RANDOM</u></font>
<mark style="background:#d4b106">Возвращает случайное число между 0 и 1.</mark>
```PostgreSQL 17.5
RANDOM()
```

***Пример:***
```PostgreSQL 17.5
SELECT RANDOM()
```
*Пример вывода:* `0.7279807846579827`

## <font color="#f79646"><u>ROUND</u></font>
<mark style="background:#d4b106">Округляет число до ближайшего целого или до указанной точности.</mark>
```PostgreSQL 17.5
ROUND(number [, precision])
```
- `number` - Входное число;
- `precision` - Количество десятичных знаков (опционально).

***Пример:***
```PostgreSQL 17.5
SELECT ROUND(5.75, 1)
```
*Вывод:* `5.8`

## <font color="#f79646"><u>SIGN</u></font>
<mark style="background:#d4b106">Возвращает знак числа (-1, 0 или 1). Функция не возвращает само число, а говорит, какое оно:</mark>
`1` - если положительное;
`-1` - если отрицательное;
`0` - если ноль.
```PostgreSQL 17.5
SIGN(num)
```

***Пример:***
```PostgreSQL 17.5
SELECT SIGN(-2)
```
*Вывод:* `-1`

## <font color="#f79646"><u>SIN</u></font>
<mark style="background:#d4b106">Возвращает синус угла в радианах.</mark>
```PostgreSQL 17.5
SIN(angle)
```

***Пример:***
```sql
SELECT SIN(PI() / 2)
```
*Вывод:* `1`

## <font color="#f79646"><u>SQRT</u></font>
<mark style="background:#d4b106">Возвращает квадратный корень числа.</mark>
```PostgreSQL 17.5
SQRT(num)
```

## <font color="#f79646"><u>TAN</u></font>
<mark style="background:#d4b106">Возвращает тангенс угла в радианах.</mark>
```PostgreSQL 17.5
TAN(angle)
```

***Пример:***
```PostgreSQL 17.5
SELECT TAN(PI() / 2)
```
*Вывод:* `16331239353195370`

## <font color="#f79646"><u>TRUNC</u></font>
<mark style="background:#d4b106">Обрезает число до указанного количества десятичных знаков.</mark>
<mark style="background:#d4b106">Это не округление.</mark>
```sql
TRUNC(num, decimals)
```
- `num` - Число;
- `decimals` - Количество десятичных знаков.

***Пример:***
```sql
SELECT TRUNC(22.29, 1)
```
*Вывод:* `22.2`

---
# <font color="#00b050">Функции дат и времени</font>

## <font color="#00b050"><u>AGE</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Возвращает разницу между двумя метками времени как интервал.</mark>
```PostgreSQL 17.5
AGE(timestamp, timestamp)
```
- `timestamp1` - Более поздняя метка времени;
- `timestamp2` - Более ранняя метка времени.

***Пример:***
```PostgreSQL 17.5
SELECT AGE('2022-12-05', '2012-06-12')
```
*Вывод:* `10 years 5 mons 23 days`

## <font color="#00b050"><u>CURRENT_DATE</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Возвращает текущую дату.</mark>
```PostgreSQL 17.5
CURRENT_DATE
```

***Пример:***
```PostgreSQL 17.5
SELECT CURRENT_DATE
```
*Пример вывода:* `2026-09-10T00:00:00.000Z`

## <font color="#00b050"><u>CURRENT_TIME</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Возвращает текущее время.</mark>
```PostgreSQL 17.5
CURRENT_TIME
```

***Пример:***
```PostgreSQL 17.5
SELECT CURRENT_TIME
```
*Пример вывода:* `17:05:52.646357+00`

## <font color="#00b050"><u>DATE</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Извлекает часть даты из даты/времени.</mark>
```PostgreSQL 17.5
DATE(datetime)
```

***Пример:***
```PostgreSQL 17.5
SELECT DATE('2022-12-05 10:37:22')
```
*Вывод:* `2022-12-05T00:00:00.000Z`

## <font color="#00b050"><u>DATE_PART</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Извлекает подполя из значения даты/времени.</mark>
```PostgreSQL 17.5
DATE_PART(field, source)
```
- `field` - Поле для извлечения (year, month, day и т.д.);
- `source` - Значение даты/времени.

***Пример:***
```PostgreSQL 17.5
SELECT DATE_PART('year', TIMESTAMP '2023-01-01')
```
*Вывод:* `2023`

## <font color="#00b050"><u>DATE_TRUNC</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Обрезает дату/время до указанной точности.</mark>
```PostgreSQL 17.5
DATE_TRUNC(field, source)
```
- `field` - Точность (year, month, day и т.д.);
- `source` - Значение даты/времени.

***Пример:***
```PostgreSQL 17.5
SELECT DATE_TRUNC('month', TIMESTAMP '2023-02-15')
```
*Вывод:* `2023-02-01T00:00:00.000Z`

## <font color="#00b050"><u>EXTRACT</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Извлекает подполя из значения даты/времени (аналогично DATE_PART).</mark>
```PostgreSQL 17.5
EXTRACT(field FROM source)
```
- `field` - Поле для извлечения;
- `FROM source` - Значение даты/времени.

***Пример:***
```PostgreSQL 17.5
SELECT EXTRACT(
		YEAR
		FROM TIMESTAMP '2023-01-01'
	)
```
*Вывод:* `2023`

## <font color="#00b050"><u>MAKE_DATE</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Создает дату из года, месяца и дня.</mark>
```PostgreSQL 17.5
MAKE_DATE(year, month, day)
```

***Пример:***
```sql
SELECT MAKE_DATE(2025, 6, 5)
```
*Вывод:* `2025-06-05T00:00:00.000Z`

## <font color="#00b050"><u>MAKE_INTERVAL</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Создает интервал из указанных компонентов.</mark>
```PostgreSQL 17.5
MAKE_INTERVAL(years, months, weeks, days, hours, mins, secs)
```
- `years` - Компонент лет;
- `months` - Компонент месяцев;
- `weeks` - Компонент недель;
- `days` - Компонент дней;
- `hours` - Компонент часов;
- `mins` - Компонент минут;
- `secs` - Компонент секунд.

***Пример:***
```PostgreSQL 17.5
SELECT MAKE_INTERVAL(0, 0, 0, 0, 0, 0, 3661)
```
*Вывод:* `01:01:01`

## <font color="#00b050"><u>MAKE_TIME</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Создает время из часа, минуты и секунды.</mark>
```PostgreSQL 17.5
MAKE_TIME(hour, minute, second)
```

***Пример:***
```PostgreSQL 17.5
SELECT MAKE_TIME(12, 30, 45)
```
*Вывод:* `12:30:45`

## <font color="#00b050"><u>NOW</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Возвращает текущую дату и время с временной зоной.</mark>
```PostgreSQL 17.5
NOW()
```

***Пример:***
```PostgreSQL 17.5
SELECT NOW()
```
*Пример вывода:* `2026-09-10T17:16:24.094Z`

## <font color="#00b050"><u>TO_CHAR</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Преобразует дату/время или число в строку по формату.</mark>
```PostgreSQL 17.5
TO_CHAR(timestamp, format)
```
- `timestamp` - Значение для преобразования;
- `format` - Строка формата.

***Пример:***
```PostgreSQL 17.5
SELECT TO_CHAR(NOW(), 'YYYY-MM-DD')
```
*Пример вывода:* `2026-09-10`

## <font color="#00b050"><u>TO_DATE</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Преобразует строку в дату с использованием указанного формата.</mark>
```PostgreSQL 17.5
TO_DATE(string, format)
```
- `string` - Строка для преобразования;
- `format` - Формат.

***Пример:***
```PostgreSQL 17.5
SELECT TO_DATE('November 13, 1998', 'Month DD, YYYY')
```
*Вывод:* `1998-11-13T00:00:00.000Z`

## <font color="#00b050"><u>TO_TIMESTAMP</u></font>
<mark style="background:rgba(4, 137, 6, 0.7)">Преобразует Unix-метку времени в метку времени.</mark>
```PostgreSQL 17.5
TO_TIMESTAMP(unix_timestamp)
```
- `unix_timestamp` - Unix-метка времени.

***Пример:***
```PostgreSQL 17.5
SELECT TO_TIMESTAMP(1717584000)
```
*Вывод:* `2024-06-05T10:40:00.000Z`

---
# <font color="#ffff00">Оконные функции</font>

## <font color="#ffff00"><u>DENSE_RANK</u></font>
<mark style="background:#fff88f">Назначает плотный ранг каждой строке в разделе. Одинаковые значения получают одинаковый ранг, при этом пропусков в нумерации нет.</mark>

```PostgreSQL 17.5
DENSE_RANK()
```

***Пример:***
```PostgreSQL 17.5
SELECT DENSE_RANK() OVER(
		ORDER BY unit_price DESC
	)
FROM Payments;
```
- `ORDER BY ... DESC` — рейтинг от большего к меньшему.
- `OVER(...)` — задаёт правила, по которым строится рейтинг.
*В отличие от `RANK()`, **ранги после одинаковых значений не пропускаются**.*

*Пример сортировки:*
```
100 → 1
80  → 2
80  → 2
50  → 3
30  → 4
```

## <font color="#ffff00"><u>FIRST_VALUE</u></font>
<mark style="background:#fff88f">Возвращает первое значение в упорядоченном наборе значений.</mark>
```PostgreSQL 17.5
FIRST_VALUE(column)
```
- `column` - Столбец.

***Пример:***
```sql
SELECT FIRST_VALUE(member_name) OVER(
		PARTITION BY STATUS
		ORDER BY birthday
	)
FROM FamilyMembers;
```
*Допустим, таблица `member_name`:*

| **member_name** | **status** | **birthday** |
| --------------- | ---------- | ------------ |
| Вася            | parent     | 1980         |
| Маша            | parent     | 1975         |
| Петя            | child      | 2010         |
| Катя            | child      | 2005         |
- `PARTITION BY status` - ***Разделить на группы** по `status` (на этом этапе фактически получаем две таблицы, разделённые по признаку `status`);*
- `ORDER BY birthday` - *Внутри каждой группы **сортируем по дате** рождения **от старшего к младшему**;*
- `FIRST_VALUE(member_name)` - *возвращает первое значение для всей группы **каждой строке** этой группы*

*Вывод:*

| **member_name** | **status** | **FIRST_VALUE** |
| --------------- | ---------- | --------------- |
| Вася            | parent     | Маша            |
| Маша            | parent     | Маша            |
| Петя            | child      | Катя            |
| Катя            | child      | Катя            |

## <font color="#ffff00"><u>LAG</u></font>
<mark style="background:#fff88f">Предоставляет доступ к строке на указанном смещении до текущей строки.</mark>
```PostgreSQL 17.5
LAG(column [, offset ] [, default])
```
- `column` - Столбец;
- `offset` - Смещение;
- `default` - Значение по умолчанию.

***Пример:***
```PostgreSQL 17.5
SELECT LAG(member_name) OVER(
		ORDER BY birthday
	)
FROM FamilyMembers;
```

*Допустим, после сортировки по `birthday` у нас:*

| member_name | birthday |
| ----------- | -------: |
| Маша        |     1975 |
| Вася        |     1980 |
| Петя        |     2005 |
| Катя        |     2010 |

*Тогда вывод:*

| member_name | LAG(member_name) |
| ----------- | ---------------- |
| Маша        | `NULL`           |
| Вася        | Маша             |
| Петя        | Вася             |
| Катя        | Петя             |

***То есть SQL идёт сверху вниз:***
- Маша → предыдущей строки нет → NULL
- Вася → предыдущая строка = Маша
- Петя → предыдущая строка = Вася
- Катя → предыдущая строка = Петя

## <font color="#ffff00"><u>LAST_VALUE</u></font>
<mark style="background:#fff88f">Возвращает последнее значение в упорядоченном наборе значений.</mark>
```PostgreSQL 17.5
LAST_VALUE(column)
```
- `column` - Столбец.

*Объяснение:* `LAST_VALUE` - фактически противоположность `FIRST_VALUE`.
Но возвращает <u>не первое, а последнее</u> значение для всей группы **каждой строке** этой группы

## <font color="#ffff00"><u>LEAD</u></font>
<mark style="background:#fff88f">Предоставляет доступ к строке на указанном смещении после текущей строки.</mark>
```PostgreSQL 17.5
LEAD(column [, offset ] [, default])
```
- `column` - Столбец;
- `offset` - Смещение;
- `default` - Значение по умолчанию.

***Пример:***
```PostgreSQL 17.5
SELECT LEAD(member_name) OVER(
		ORDER BY birthday
	)
FROM FamilyMembers;
```

*Объяснение:* `LEAD` - фактически противоположность `LAG`.
Но смещение происходит <u>не вперёд, а назад</u>.

*Допустим, после сортировки по `birthday` у нас:*

| member_name | birthday |
| ----------- | -------: |
| Маша        |     1975 |
| Вася        |     1980 |
| Петя        |     2005 |
| Катя        |     2010 |

*Тогда вывод:*

| member_name | LAG(member_name) |
| ----------- | ---------------- |
| Маша        | Вася             |
| Вася        | Петя             |
| Петя        | Катя             |
| Катя        | `NULL`           |

## <font color="#ffff00"><u>RANK</u></font>
<mark style="background:#fff88f">Назначает ранг каждой строке в разделе.</mark> В отличие от `DENSE_RANK`, она присваивает одинаковым значениям **одинаковый ранг**, но после одинаковых значений **пропускает номера**.
```PostgreSQL 17.5
RANK()
```

***Пример:***
```PostgreSQL 17.5
SELECT RANK() OVER(
		ORDER BY unit_price DESC
	)
FROM Payments;
```
*Пример вывода после сортировки:*
- 100 → 1
- 80  → 2
- 80  → 2
- 50  → 4
- 30  → 5
**Почему `50 → 4`, а не `3`?**
	Потому что два человека заняли **2-е место**, поэтому следующее место — **4-е**. Это отличие "плотного" ранга от обычного.

## <font color="#ffff00"><u>ROW_NUMBER</u></font>
<mark style="background:#fff88f">Назначает уникальный номер каждой строке в разделе.</mark> **Просто последовательно нумерует строки: 1, 2, 3, 4...**
```PostgreSQL 17.5
ROW_NUMBER()
```

---
# <font color="#6425d0">Агрегатные функции</font>

## <font color="#6425d0"><u>AVG</u></font>
<mark style="background:#9254de">Возвращает среднее значение набора значений.</mark>
<mark style="background:#9254de">Просто среднее арифметическое набора чисел.</mark>
```PostgreSQL 17.5
AVG(expression)
```

## <font color="#6425d0"><u>COUNT</u></font>
<mark style="background:#9254de">Возвращает количество строк или ненулевых значений.</mark>
```PostgreSQL 17.5
COUNT(expression)
```
- expression - Выражение для подсчета *(`*` для всех строк)*.

***Пример:***
```PostgreSQL 17.5
SELECT COUNT(*)
FROM FamilyMembers;
```

*Допустим, `FamilyMembers`:*
- `Вася`
- `Маша`
- `NULL`
- `Петя`

*Тогда результат:* `3`

## <font color="#6425d0"><u>MAX</u></font>
<mark style="background:#9254de">Возвращает максимальное (наибольшее) значение в наборе.</mark>
```PostgreSQL 17.5
MAX(expression)
```

## <font color="#6425d0"><u>MIN</u></font>
<mark style="background:#9254de">Возвращает минимальное (наименьшее) значение в наборе.</mark>
```PostgreSQL 17.5
MIN(expression)
```

## <font color="#6425d0"><u>STRING_AGG</u></font>
<mark style="background:#9254de">Объединяет набор строк с разделителем.</mark>
```PostgreSQL 17.5
STRING_AGG(expression, delimiter)
```
- `expression` - Строковое выражение;
- `delimiter` - Разделитель для вставки.

***Пример:***
```PostgreSQL 17.5
SELECT STRING_AGG(member_name, ', ')
FROM FamilyMembers;
```

*Допустим, `FamilyMembers`:*
- `Вася`
- `Маша`
- `Петя`

*Тогда результат:* `Вася, Маша, Петя`

## <font color="#6425d0"><u>SUM</u></font>
<mark style="background:#9254de">Возвращает сумму набора значений.</mark>
```PostgreSQL 17.5
SUM(expression)
```

---
# <font color="#ff0000">Продвинутые функции</font>

## <font color="#ff0000"><u>CAST</u></font>
<mark style="background:#ff4d4f">Преобразует значение в указанный тип.</mark>
```PostgreSQL 17.5
CAST(value AS type)
```
- `value` - Значение для преобразования;
- `type` - Целевой тип.

***Пример:***
```PostgreSQL 17.5
SELECT CAST(12005.6 AS NUMERIC)
```

## <font color="#ff0000"><u>COALESCE</u></font>
<mark style="background:#ff4d4f">Возвращает первое не-null значение из списка.</mark>
```PostgreSQL 17.5
COALESCE(val1[, val2, ...., val_n])
```
- `val1` - Значения для проверки.

***Пример:***
```PostgreSQL 17.5
SELECT COALESCE(NULL, NULL, 1, 2)
```

## <font color="#ff0000"><u>NULLIF</u></font>
<mark style="background:#ff4d4f">Возвращает null, если два значения равны.</mark>
```PostgreSQL 17.5
NULLIF(value_1, value_2)
```

## <font color="#ff0000"><u>WITH</u></font>
<mark style="background:#ff4d4f">Определяет общее табличное выражение (CTE).</mark>
Это способ создать **временную таблицу внутри одного SQL-запроса**. Она называется **CTE (Common Table Expression)**.
```PostgreSQL 17.5
WITH name_cte AS (subquery)
```
- `name_cte` - Имя CTE;
- `subquery` - Подзапрос.

***Пример:***
```PostgreSQL 17.5
WITH family_stats AS (
	SELECT STATUS,
		COUNT(*) AS cnt
	FROM FamilyMembers
	GROUP BY STATUS
)
SELECT *
FROM family_stats;
```
*Объяснение:*
`WITH family_stats AS (...)` создаёт **временный результат** и называет его `family_stats`.
А затем `SELECT * FROM family_stats;` работает с ним как с обычной таблицей.

