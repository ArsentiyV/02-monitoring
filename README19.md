# Домашнее задание к занятию "`Репликация и масштабирование. Часть 1`" - `Варитлов Арсентий`


### Задание 1.

На лекции рассматривались режимы репликации master-slave, master-master, опишите их различия.

Ответ. 

Master-Slave. 
В данном случае может существовать только один Master, а вот Slave-машин может быть несколько. 
Вся основная работа происходит на машине Master, на машинах Slave информация обновляется с задержкой и
можно только считываться. В случае если Master по какой-то причине выйдет из строя, то Slave может быть 
повышен до Master.

Master-Master.
В данной схеме каждый Master одновременно является Slave и наоборот - операции чтения, записи, изменения и т.д. 
можно производить на всех машинах одновременно.Если один Master выйдет из строя, его сразу заменит другой. 
Но в данной схеме могут возникнуть конфликты при большом объеме изменений в базе.

### Задание 2.

Выполните конфигурацию master-slave репликации, примером можно пользоваться из лекции.

Ответ. 

Конфигурация Master 

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-1.jpg)

Статус Master 

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-2.jpg)

Конфигурация Slave

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-3.jpg)

Статус Slave

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-4.jpg)
![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-4-1.jpg)

Базы на Master

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-5.jpg)

Базы на Slave

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-6.jpg)

Создал базу arsentiy на Master

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-7.jpg)

Созданная база arsentiy  отобразилась на Slave

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/sql-cl-8.jpg)
