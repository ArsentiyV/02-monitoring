# Домашнее задание к занятию 1. «Введение в виртуализацию» - `Варитлов Арсентий`


### Задание 1.

Задача 1
Установите на личный Linux-компьютер или учебную локальную ВМ с Linux следующие сервисы(желательно 
ОС ubuntu 20.04):
- VirtualBox,
- Vagrant, рекомендуем версию 2.3.4
- Packer версии 1.9.х + плагин от Яндекс Облако по инструкции
- уandex cloud cli Так же инициализируйте профиль с помощью yc init .
Примечание: Облачная ВМ с Linux в данной задаче не подойдёт из-за ограничений облачного провайдера. 
У вас просто не установится virtualbox.

Ответ. 

![Скриншот 1](https://github.com/ArsentiyV/02-monitoring/blob/main/img/virt2-1-1.jpg)`

![Скриншот 2](https://github.com/ArsentiyV/02-monitoring/blob/main/img/virt2-1-2.jpg)`


### Задание 2. 

Убедитесь, что у вас есть ssh ключ в ОС или создайте его с помощью команды ssh-keygen -t ed25519
Создайте виртуальную машину Virtualbox с помощью Vagrant и Vagrantfile в директории src.
Зайдите внутрь ВМ и убедитесь, что Docker установлен с помощью команды:
docker version && docker compose version
Если Vagrant выдаёт ошибку (блокировка трафика):
URL: ["https://vagrantcloud.com/bento/ubuntu-20.04"]
Error: The requested URL returned error: 404:
Выполните следующие действия:
Скачайте с сайта файл-образ "bento/ubuntu-20.04".
Добавьте его в список образов Vagrant: "vagrant box add bento/ubuntu-20.04 <путь к файлу>".
Важно:
Если ваша хостовая рабочая станция - это windows ОС, то у вас могут возникнуть проблемы со вложенной 
виртуализацией. Ознакомиться со cпособами решения можно по ссылке.
Если вы устанавливали hyper-v или docker desktop, то все равно может возникать ошибка:
Stderr: VBoxManage: error: AMD-V VT-X is not available (VERR_SVM_NO_SVM)
Попробуйте в этом случае выполнить в Windows от администратора команду bcdedit /set hypervisorlaunchtype 
off и перезагрузиться.
Если ваша рабочая станция в меру различных факторов не может запустить вложенную виртуализацию - 
допускается неполное выполнение(до ошибки запуска ВМ)


Ответ. 

![Скриншот 3](https://github.com/ArsentiyV/02-monitoring/blob/main/img/virt2-2-1.jpg)`


### Задание 3.

Отредактируйте файл или mydebian.json.pkr.hcl в директории src (packer умеет и в json, и в hcl форматы):
добавьте в скрипт установку docker (возьмите готовый bash-скрипт из Vagrantfile или документации к docker),
дополнительно установите в данном образе htop и tmux.(не забудьте про ключ автоматического подтверждения 
установки для apt)
Найдите свой образ в web консоли yandex_cloud
Необязательное задание(*): найдите в документации yandex cloud как найти свой образ с помощью утилиты 
командной строки "yc cli".
Создайте новую ВМ (минимальные параметры) в облаке, используя данный образ.
Подключитесь по ssh и убедитесь в наличии установленного docker.
Удалите ВМ и образ.
ВНИМАНИЕ! Никогда не выкладываете oauth token от облака в git-репозиторий! Утечка секретного токена 
может привести к финансовым потерям. После выполнения задания обязательно удалите секретные данные из 
файла mydebian.json и mydebian.json.pkr.hcl. (замените содержимое токена на "ххххх")


Ответ. 

![Скриншот 4](https://github.com/ArsentiyV/02-monitoring/blob/main/img/virt2-3-0.jpg)`

![Скриншот 5](https://github.com/ArsentiyV/02-monitoring/blob/main/img/virt2-3-1.jpg)`

![Скриншот 4](https://github.com/ArsentiyV/02-monitoring/blob/main/img/virt2-3-2.jpg)`

![Скриншот 4](https://github.com/ArsentiyV/02-monitoring/blob/main/img/virt2-3-3.jpg)`

---
