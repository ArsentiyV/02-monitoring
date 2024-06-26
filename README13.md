# Домашнее задание к занятию "`Очереди RabbitMQ`" - `Варитлов Арсентий`

##Задание 1. Установка RabbitMQ
Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ. 
Добавьте management plug-in и зайдите в веб-интерфейс.Итогом выполнения домашнего 
задания будет приложенный скриншот веб-интерфейса RabbitMQ.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-1.jpg)`


##Задание 2. Отправка и получение сообщений
Используя приложенные скрипты, проведите тестовую отправку и получение сообщения. 
Для отправки сообщений необходимо запустить скрипт producer.py. Для работы скриптов 
вам необходимо установить Python версии 3 и библиотеку Pika. Также в скриптах нужно 
указать IP-адрес машины, на которой запущен RabbitMQ, заменив localhost на нужный IP.
$ pip install pika
Зайдите в веб-интерфейс, найдите очередь под названием hello и сделайте скриншот. 
После чего запустите второй скрипт consumer.py и сделайте скриншот результата выполнения скрипта
В качестве решения домашнего задания приложите оба скриншота, сделанных на этапе выполнения.
Для закрепления материала можете попробовать модифицировать скрипты, чтобы поменять название 
очереди и отправляемое сообщение.

![Скриншот 2](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-2-1.jpg)`

![Скриншот 3](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-2-2.jpg)`

![Скриншот 4](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-2-3.jpg)`


##Задание 3. Подготовка HA кластера
Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ. 
Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.
После этого ваши машины могут пинговаться по имени. Затем объедините две машины в кластер и создайте 
политику ha-all на все очереди. В качестве решения домашнего задания приложите скриншоты из веб-интерфейса 
с информацией о доступных нодах в кластере и включённой политикой. 

![Скриншот 5](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-3-1.jpg)`

![Скриншот 6](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-3-2.jpg)`

Также приложите вывод команды с двух нод: $ rabbitmqctl cluster_status

![Скриншот 7](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-3-3.jpg)`

![Скриншот 8](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-3-4.jpg)`

Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:
$ rabbitmqadmin get queue='hello'
После чего попробуйте отключить одну из нод, желательно ту, к которой подключались из скрипта, затем поправьте 
параметры подключения в скрипте consumer.py на вторую ноду и запустите его.
Приложите скриншот результата работы второго скрипта.

![Скриншот 9](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-3-5.jpg)`

![Скриншот 10](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-3-6.jpg)`

![Скриншот 11](https://github.com/ArsentiyV/02-monitoring/blob/main/img/rabbitmq-3-7.jpg)`


