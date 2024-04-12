# Домашнее задание к занятию 2. «SQL» - `Варитлов Арсентий`


### Задание 1.

Используя Docker, поднимите инстанс PostgreSQL (версию 12) c 2 volume, в который будут складываться данные БД и бэкапы.
Приведите получившуюся команду или docker-compose-манифест.

Ответ. 

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_0.jpg)`

Далее все операции с базой производились одним скриптом:

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_1_1.jpg)`
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_1_2.jpg)`


### Задание 2. 

В БД из задачи 1:

- создайте пользователя test-admin-user и БД test_db;
- в БД test_db создайте таблицу orders и clients (спeцификация таблиц ниже);
- предоставьте привилегии на все операции пользователю test-admin-user на таблицы 
  БД test_db;
- создайте пользователя test-simple-user;
- предоставьте пользователю test-simple-user права на SELECT/INSERT/UPDATE/DELETE 
  этих таблиц БД test_db.

Таблица orders:
- id (serial primary key);
- наименование (string);
- цена (integer).

Таблица clients:
- id (serial primary key);
- фамилия (string);
- страна проживания (string, index);
- заказ (foreign key orders).

Приведите:
- итоговый список БД после выполнения пунктов выше;
- описание таблиц (describe);
- SQL-запрос для выдачи списка пользователей с правами над таблицами test_db;
- список пользователей с правами над таблицами test_db.

Ответ.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_2_1.jpg)`
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_2_2.jpg)`


### Задание 3.

Используя SQL-синтаксис, наполните таблицы следующими тестовыми данными:

Таблица orders

Наименование	цена
Шоколад	        10
Принтер	        3000
Книга	        500
Монитор	        7000
Гитара	        4000
Таблица         clients

ФИО	                Страна проживания
Иванов Иван Иванович	USA
Петров Петр Петрович	Canada
Иоганн Себастьян Бах	Japan
Ронни Джеймс Дио	Russia
Ritchie Blackmore	Russia

Используя SQL-синтаксис:
- вычислите количество записей для каждой таблицы.

 Приведите в ответе:
- запросы,
- результаты их выполнения.

Ответ.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_3_1.jpg)`

### Задание 4.

Часть пользователей из таблицы clients решили оформить заказы из таблицы orders.
Используя foreign keys, свяжите записи из таблиц, согласно таблице:

ФИО	                Заказ
Иванов Иван Иванович	Книга
Петров Петр Петрович	Монитор
Иоганн Себастьян Бах	Гитара

Приведите SQL-запросы для выполнения этих операций.
Приведите SQL-запрос для выдачи всех пользователей, которые совершили заказ, а 
также вывод этого запроса.
Подсказка: используйте директиву UPDATE.

Ответ.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_4_1.jpg)`


### Задание 5.

Получите полную информацию по выполнению запроса выдачи всех пользователей из 
задачи 4 (используя директиву EXPLAIN).
Приведите получившийся результат и объясните, что значат полученные значения.

Ответ.

EXPLAIN - предоставляет служебную информацию о запросе к БД, в том числе время на 
выполнение запроса, что при оптимизации работы БД является очень полезной информацией.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_5_1.jpg)`

### Задание 6.

Создайте бэкап БД test_db и поместите его в volume, предназначенный для бэкапов
(см. задачу 1).
Остановите контейнер с PostgreSQL, но не удаляйте volumes.
Поднимите новый пустой контейнер с PostgreSQL.
Восстановите БД test_db в новом контейнере.
Приведите список операций, который вы применяли для бэкапа данных и восстановления.

Ответ. 

Делаем бэкап
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_6_1.jpg)`

Останавливаем и удаляем контейнер 
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_6_2.jpg)`

Удаляем volume
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_6_3.jpg)`

Запускаем новый контейнер,подключаемся к нему и проверяем наличие информации для восстановления.
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_6_4.jpg)`

Проводим восстановление из бекапа
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_6_5.jpg)`

Проверяем восстановленные данные
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/pgsql_6_6.jpg)`


---
