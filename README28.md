# Домашнее задание к занятию 4. «PostgreSQL» - `Варитлов Арсентий`


### Задание 1.

Используя Docker, поднимите инстанс PostgreSQL (версию 13). Данные БД сохраните в volume.
Подключитесь к БД PostgreSQL, используя psql.
Воспользуйтесь командой \? для вывода подсказки по имеющимся в psql управляющим командам.
Найдите и приведите управляющие команды для:
- вывода списка БД,
- подключения к БД,
- вывода списка таблиц,
- вывода описания содержимого таблиц,
- выхода из psql.

Ответ. 

\l[+]   [PATTERN]      list databases

\c[onnect] {[DBNAME|- USER|- HOST|- PORT|-] | conninfo} connect to new database (currently "postgres")

\dt[S+] [PATTERN]      list tables

\d[S+]                 list tables, views, and sequences

\q                     quit psql

### Задание 2. 

Используя psql, создайте БД test_database.
Изучите бэкап БД.
Восстановите бэкап БД в test_database.
Перейдите в управляющую консоль psql внутри контейнера.
Подключитесь к восстановленной БД и проведите операцию ANALYZE для сбора статистики по таблице.
Используя таблицу pg_stats, найдите столбец таблицы orders с наибольшим средним значением размера элементов в байтах.
Приведите в ответе команду, которую вы использовали для вычисления, и полученный результат.

Ответ.

![Скриншот 4](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql2_1.jpg)`

![Скриншот 5](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql2_1_2.jpg)`

![Скриншот 6](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql2_1_3.jpg)`


### Задание 3.

Архитектор и администратор БД выяснили, что ваша таблица orders разрослась до невиданных размеров и поиск по ней занимает 
долгое время. Вам как успешному выпускнику курсов DevOps в Нетологии предложили провести разбиение таблицы на 2: шардировать 
на orders_1 - price>499 и orders_2 - price<=499.
Предложите SQL-транзакцию для проведения этой операции.
Можно ли было изначально исключить ручное разбиение при проектировании таблицы orders?

Ответ.

Мможно было избежать разбиения таблицы вручную, необходимо было определить тип на моменте проектирования и 
создания - partitioned table

![Скриншот 7](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql2_2_1.jpg)`


### Задание 4.

Используя утилиту pg_dump, создайте бекап БД test_database.
Как бы вы доработали бэкап-файл, чтобы добавить уникальность значения столбца title для таблиц test_database?

Ответ.

Для определения занчения столбца title можно было бы использовать индекс, для обеспечения уникальности

![Скриншот 9](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql2_3_1.jpg)`


---