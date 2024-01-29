# Домашнее задание к занятию "`Индексы`" - `Варитлов Арсентий`


### Задание 1.

Напишите запрос к учебной базе данных, который вернёт процентное отношение общего размера всех 
индексов к общему размеру всех таблиц.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/SQL-ind-1_1.jpg)


### Задание 2.

Выполните explain analyze следующего запроса:
```sql
select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount) over (partition by c.customer_id, f.title)
from payment p, rental r, customer c, inventory i, film f
where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id
```
- перечислите узкие места;
- оптимизируйте запрос: внесите корректировки по использованию операторов, при необходимости добавьте индексы.


Ответ. 

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/SQL-ind-2-1.jpg)

Насколько я понимаю данный запрос выдает платежи людей, взявших в аренду фильмы за определенную дату. 
Если нам надо получить только этe информацию , то таблицы rental, inventory, film надо исключить из запроса 
т. к. исходный запрос перебирает слишком много строк что сказывается на времени выполнения запроса.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/SQL-ind-2-2.jpg)
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/SQL-ind-2-3.jpg)

