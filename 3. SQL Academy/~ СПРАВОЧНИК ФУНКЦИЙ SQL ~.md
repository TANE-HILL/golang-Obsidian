# Строковые функции

## <u>CHR</u>
Возвращает символ с указанным ASCII-кодом.
```PostgreSQL 17.5
CHR(ascii)
```

## <u>CONCAT</u>
Объединяет переменное количество аргументов в одну строку. Null значения игнорируются.
```PostgreSQL 17.5
CONCAT(expression [, ...])
```

## <u>LENGTH</u>
Возвращает количество символов в строке.
```PostgreSQL 17.5
LENGTH(string)
```

## <u>LOWER</u>
Преобразует строку в нижний регистр.
```PostgreSQL 17.5
LOWER(string)
```

## <u>LPAD</u>
Дополняет строку слева до указанной длины с помощью строки заполнителя.
```PostgreSQL 17.5
LPAD(str, len, pad_str)
```
- `str` - Строка для дополнения;
- `len` - Целевая длина;
- `pad_str` - Строка заполнителя.

***Пример:*** `SELECT LPAD('9', 5, '0')`
*Вывод:* `00009`

## <u>LTRIM</u>
Удаляет ведущие пробелы из строки.
```PostgreSQL 17.5
LTRIM(str)
```

## <u>POSITION</u>
Возвращает начальную позицию подстроки в строке или ноль, если не найдено.
```PostgreSQL 17.5
POSITION(substring IN string)
```
- `substring` - Подстрока для поиска;
- `IN string` - Исходная строка.

***Пример:*** `SELECT POSITION('om' IN 'Thomas')`
*Вывод:* `3`

## <u>REPEAT</u>
Повторяет строку указанное количество раз.
```PostgreSQL 17.5
REPEAT(str, count)
```
- `str` - Строка для повторения;
- `count` - Количество повторений.

## <u>REPLACE</u>
Заменяет все вхождения подстроки другой подстрокой в строке.
```PostgreSQL 17.5
REPLACE(string, from, to)
```
- `string` - Исходная строка;
- `from` - Подстрока для замены;
- `to` - Заменяющая подстрока.

***Пример:*** `SELECT REPLACE('abcdef', 'cd', 'XX')`
*Вывод:* `abXXef`

## <u>REVERSE</u>
Переворачивает строку.
```PostgreSQL 17.5
REVERSE(str)
```

## <u>RPAD</u>
Дополняет строку справа до указанной длины с помощью строки заполнителя.
```PostgreSQL 17.5
RPAD(str, len, pad_str)
```
- `str` - Строка для дополнения;
- `len` - Целевая длина;
- `pad_str` - Строка заполнителя.

***Пример:*** `SELECT RPAD('9', 5, '0')`
*Вывод:* `90000`

## <u>RTRIM</u>
Возвращает строку, у которой удалены все пробелы с правого края
```PostgreSQL 17.5
RTRIM(str)
```

## <u>SPLIT_PART</u>
Разделяет строку по заданному разделителю и возвращает указанную часть.
```PostgreSQL 17.5
SPLIT_PART(string, delimiter, part_number)
```
- `string` - Исходная строка;
- `delimiter` - Разеделитель для разбиения;
- `part_number` - Номер части для возврата (начиная с 1).

***Пример:*** `SELECT SPLIT_PART('a|b|c', '|', 2)`
*Вывод:* `b`

## <u>SUBSTRING</u>
Извлекает подстроку из строки, начиная с заданной позиции на заданную длину.
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

## <u>TRIM</u>
Удаляет самую длинную строку, содержащую только указанные символы, из начала, конца или обоих концов строки.
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

## <u>UPPER</u>
Преобразует строку в верхний регистр.
```PostgreSQL 17.5
UPPER(string)
```

---
# Числовые функции

## <u>ABS</u>
Возвращает абсолютное значение числа. Абсолютное значение - расстояние от нуля до числа на координатной прямой.
```PostgreSQL 17.5
ABS(number)
```

***Пример:***
```PostgreSQL 17.5
SELECT ABS(-5.7)
```
*Вывод:* `5.7`

## <u>CEIL</u>
Возвращает наименьшее целое, большее или равное числу.
```PostgreSQL 17.5
CEIL(number)
```

***Пример:***
```sql
SELECT CEIL(5.3)
```
*Вывод:* `6`

## <u>COS</u>
Возвращает косинус угла в радианах.
```PostgreSQL 17.5
COS(angle)
```
- `angle` - Угол в радианах.

## <u>EXP</u>
Возвращает `e` в степени числа.
```PostgreSQL 17.5
EXP(num)
```

***Пример:***
```PostgreSQL 17.5
SELECT EXP(1)
```
*Вывод:* `2.718281828459045`

## <u>FLOOR</u>
Возвращает наибольшее целое, меньшее или равное числу.
```PostgreSQL 17.5
FLOOR(number)
```

***Пример:***
```PostgreSQL 17.5
SELECT FLOOR(5.7)
```
*Вывод:* `5`

## <u>GREATEST</u>
Возвращает наибольшее значение из списка значений.
```PostgreSQL 17.5
GREATEST(num [,num])
```

***Пример:***
```PostgreSQL 17.5
SELECT GREATEST(1, 2, -1)
```
*Вывод:* `2`

## <u>LEAST</u>
Возвращает наименьшее значение из списка значений.
```PostgreSQL 17.5
LEAST(num [,num])
```

***Пример:***
```PostgreSQL 17.5
SELECT LEAST(1, 2, -1)
```
*Вывод:* `-1`

## <u>LOG</u>
Возвращает логарифм числа по указанному основанию.
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

## <u>MOD</u>
Возвращает остаток от деления.
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

## <u>PI</u>
Возвращает значение пи.
```PostgreSQL 17.5
PI()
```

***Пример:***
```PostgreSQL 17.5
SELECT PI()
```
*Вывод:* `3.141592653589793`

## <u>POWER</u>
Возвращает число, возведенное в степень.
```PostgreSQL 17.5
POWER(num, power)
```

***Пример:***
```PostgreSQL 17.5
SELECT POWER(2, 2)
```
*Вывод:* `4`

## <u>RANDOM</u>
Возвращает случайное число между 0 и 1.
```PostgreSQL 17.5
RANDOM()
```

***Пример:***
```PostgreSQL 17.5
SELECT RANDOM()
```
*Пример вывода:* `0.7279807846579827`

## <u>ROUND</u>
Округляет число до ближайшего целого или до указанной точности.
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

## <u>SIGN</u>
Возвращает знак числа (-1, 0 или 1). Функция не возвращает само число, а говорит, какое оно:
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

## <u>SIN</u>
Возвращает синус угла в радианах.
```PostgreSQL 17.5
SIN(angle)
```

***Пример:***
```sql
SELECT SIN(PI() / 2)
```
*Вывод:* `1`

## <u>SQRT</u>
Возвращает квадратный корень числа.
```PostgreSQL 17.5
SQRT(num)
```

## <u>TAN</u>
Возвращает тангенс угла в радианах.
```PostgreSQL 17.5
TAN(angle)
```

***Пример:***
```PostgreSQL 17.5
SELECT TAN(PI() / 2)
```
*Вывод:* `16331239353195370`

## <u>TRUNC</u>
Обрезает число до указанного количества десятичных знаков.
Это не округление.
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
# Функции дат и времени

## <u>AGE</u>
Возвращает разницу между двумя метками времени как интервал.
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

## <u>CURRENT_DATE</u>
Возвращает текущую дату.
```PostgreSQL 17.5
CURRENT_DATE
```

***Пример:***
```PostgreSQL 17.5
SELECT CURRENT_DATE
```
*Пример вывода:* `2026-09-10T00:00:00.000Z`

## <u>CURRENT_TIME</u>
Возвращает текущее время.
```PostgreSQL 17.5
CURRENT_TIME
```

***Пример:***
```PostgreSQL 17.5
SELECT CURRENT_TIME
```
*Пример вывода:* `17:05:52.646357+00`

## <u>DATE</u>
Извлекает часть даты из даты/времени.
```PostgreSQL 17.5
DATE(datetime)
```

***Пример:***
```PostgreSQL 17.5
SELECT DATE('2022-12-05 10:37:22')
```
*Вывод:* `2022-12-05T00:00:00.000Z`

## <u>DATE_PART</u>
Извлекает подполя из значения даты/времени.
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

## <u>DATE_TRUNC</u>
Обрезает дату/время до указанной точности.
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

## <u>EXTRACT</u>
Извлекает подполя из значения даты/времени (аналогично DATE_PART).
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

## <u>MAKE_DATE</u>
Создает дату из года, месяца и дня.
```PostgreSQL 17.5
MAKE_DATE(year, month, day)
```

***Пример:***
```sql
SELECT MAKE_DATE(2025, 6, 5)
```
*Вывод:* `2025-06-05T00:00:00.000Z`

## <u>MAKE_INTERVAL</u>
Создает интервал из указанных компонентов.
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

## <u>MAKE_TIME</u>
Создает время из часа, минуты и секунды.
```PostgreSQL 17.5
MAKE_TIME(hour, minute, second)
```

***Пример:***
```PostgreSQL 17.5
SELECT MAKE_TIME(12, 30, 45)
```
*Вывод:* `12:30:45`

## <u>NOW</u>
Возвращает текущую дату и время с временной зоной.
```PostgreSQL 17.5
NOW()
```

***Пример:***
```PostgreSQL 17.5
SELECT NOW()
```
*Пример вывода:* `2026-09-10T17:16:24.094Z`

## <u>TO_CHAR</u>
Преобразует дату/время или число в строку по формату.
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

## <u>TO_DATE</u>
Преобразует строку в дату с использованием указанного формата.
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

## <u>TO_TIMESTAMP</u>
Преобразует Unix-метку времени в метку времени.
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
# Оконные функции

## <u>DENSE_RANK</u>
Назначает плотный ранг каждой строке в разделе. Одинаковые значения получают одинаковый ранг, при этом пропусков в нумерации нет.

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

## <u>FIRST_VALUE</u>
Возвращает первое значение в упорядоченном наборе значений.
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

## <u>LAG</u>
Предоставляет доступ к строке на указанном смещении до текущей строки.
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

## <u>LAST_VALUE</u>
Возвращает последнее значение в упорядоченном наборе значений.
```PostgreSQL 17.5
LAST_VALUE(column)
```
- `column` - Столбец.

*Объяснение:* `LAST_VALUE` - фактически противоположность `FIRST_VALUE`.
Но возвращает <u>не первое, а последнее</u> значение для всей группы **каждой строке** этой группы

## <u>LEAD</u>
Предоставляет доступ к строке на указанном смещении после текущей строки.
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

## <u>RANK</u>
Назначает ранг каждой строке в разделе. В отличие от `DENSE_RANK`, она присваивает одинаковым значениям **одинаковый ранг**, но после одинаковых значений **пропускает номера**.
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

## <u>ROW_NUMBER</u>
Назначает уникальный номер каждой строке в разделе. **Просто последовательно нумерует строки: 1, 2, 3, 4...**
```PostgreSQL 17.5
ROW_NUMBER()
```

---
# Агрегатные функции

## <u>AVG</u>
Возвращает среднее значение набора значений.
Просто **среднее арифметическое** набора чисел.
```PostgreSQL 17.5
AVG(expression)
```

## <u>COUNT</u>
Возвращает количество строк или ненулевых значений.
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

## <u>MAX</u>
Возвращает **максимальное** (наибольшее) значение в наборе.
```PostgreSQL 17.5
MAX(expression)
```

## <u>MIN</u>
Возвращает **минимальное** (наименьшее) значение в наборе.
```PostgreSQL 17.5
MIN(expression)
```

## <u>STRING_AGG</u>
Объединяет набор строк с разделителем.
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

## <u>SUM</u>
Возвращает сумму набора значений.
```PostgreSQL 17.5
SUM(expression)
```

---
# Продвинутые функции

## <u>CAST</u>
Преобразует значение в указанный тип.
```PostgreSQL 17.5
CAST(value AS type)
```
- `value` - Значение для преобразования;
- `type` - Целевой тип.

***Пример:***
```PostgreSQL 17.5
SELECT CAST(12005.6 AS NUMERIC)
```

## <u>COALESCE</u>
Возвращает первое не-null значение из списка.
```PostgreSQL 17.5
COALESCE(val1[, val2, ...., val_n])
```
- `val1` - Значения для проверки.

***Пример:***
```PostgreSQL 17.5
SELECT COALESCE(NULL, NULL, 1, 2)
```

## <u>NULLIF</u>
Возвращает `null`, если два значения равны.
```PostgreSQL 17.5
NULLIF(value_1, value_2)
```

## <u>WITH</u>
Определяет общее табличное выражение (CTE).
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

