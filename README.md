ю# Домашнее задание к занятию "`Защита сети`" - `Варитлов Арсентий`


### Задание 1.

Проведите разведку системы и определите, какие сетевые службы запущены на защищаемой системе:
sudo nmap -sA < ip-адрес >
sudo nmap -sT < ip-адрес >
sudo nmap -sS < ip-адрес >
sudo nmap -sV < ip-адрес >
По желанию можете поэкспериментировать с опциями: https://nmap.org/man/ru/man-briefoptions.html.
В качестве ответа пришлите события, которые попали в логи Suricata и Fail2Ban, прокомментируйте результат.

Ответ. 

Сервис suricata поднят.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-1-1.jpg)

Сканирование хоста 192.168.3.102

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-1-2.jpg)

Suricata выявил попытки сканирования

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-1-3.jpg)

Fail2Ban ничего не выявил

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-1-4.jpg)


### Задание 2. 


Проведите атаку на подбор пароля для службы SSH:
hydra -L users.txt -P pass.txt < ip-адрес > ssh
Настройка hydra:
создайте два файла: users.txt и pass.txt;
в каждой строчке первого файла должны быть имена пользователей, второго — пароли. В нашем случае это могут 
быть случайные строки, но ради эксперимента можете добавить имя и пароль существующего пользователя.
Дополнительная информация по hydra: https://kali.tools/?p=1847.
Включение защиты SSH для Fail2Ban:
открыть файл /etc/fail2ban/jail.conf,
найти секцию ssh,
установить enabled в true.
Дополнительная информация по Fail2Ban:https://putty.org.ru/articles/fail2ban-ssh.html.
В качестве ответа пришлите события, которые попали в логи Suricata и Fail2Ban, прокомментируйте результат.

Ответ.

В файлы users.txt и pass.txt были внесены кроме фейковых и реальные данные пользователя. 
Hydra подобрала логин и пароль для ssh соединения.
Fail2ban включен.
В логе файла auth видна операция подбора пароля. Suricata показал сканирование ssh. 
Лог-файл Fail2ban ничего не показал.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-2-1.jpg)

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-2-2.jpg)

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-2-3.jpg)

В настройках Fail2ban в секции SSH прописано enable = true
Suricata показал сканирование ssh. Лог файла auth показывает попытки подбора пароля. 
Лог-файл Fail2ban также показывает попытку подключения. После включения попытка подобрать 
пароль была заблокирована.

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-2-4.jpg)

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-2-5.jpg)

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/znet-2-6.jpg)

---
