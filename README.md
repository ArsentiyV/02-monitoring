# Домашнее задание к занятию «Базы данных, их типы» - Варитлов А.
 

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.СУБД 
должна гарантировать целостность и чёткую структуру данных.

*Ответ*

Для обеспечения целостности и четкой структуры данных подойдет реляционная СУБД.

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и 
менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.

*Ответ*

На мой взгляд подойдут реляционная и графовая СУБД.


1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, 
сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

*Ответ*

В данном случае думаю надо применить документо-ориентированную СУБД.


1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и 
распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.

*Ответ*

В данном случае думаю надо применить графовую СУБД.


---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.


*Ответ*

1. Начало транзакции.
2. Проверка соответствия необходимой и полученной суммы для пополнения.
3. Подтверждение внесенной суммы.
4. Соединение с оператором и перевод суммы на счет клиента.
5. Подтверждение внесения сумма.
6. Закрытие транзакции.


---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

*Ответ*

- Надежная защита данных 
- Масштабируемость 
- Высокая производительность 
- Простота использования (стандартизированный язык)
- Согласованность данных

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 
1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* здесь справится лучше всего и
почему?

*Ответ*

Исходя из большого количества машин выделенных на обработку данных думаю понадобится горизонтальное масштабирование и в данном случае лучшим выбором думаю будет noSQL.
В качестве модели распределенных вичисления выбрал бы n-уровневую архитектуру, в которой разные приложения совместно работают на решение задачи как одна система.

