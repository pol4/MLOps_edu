# Учебный проект по MLOps

Описание задачи:


Предварительный анализ задачи определения мошеннических финансовых операций

# Домашнее задание No 1

Цель работы. В данном домашнем задании Вы потренируетесь формализовывать поставленные
бизнесом задачи анализа данных, определять цели и способы их достижения, декомпозировать
систему анализа данных и визуализировать задачи с использованием канбан-доски в GitHub Projects.

Фабула:
Вас пригласили на работу в качестве специалиста по данным в коммерческую компанию,
занимающуюся предоставлением банковских услуг населению. Одной из услуг компании,
пользующейся большой популярностью у населения, является проведение онлайн-платежей
с банковских счетов граждан.

К сожалению, в последнее время участились случаи мошенничества при проведении таких операций.
Руководство компании встревожено такой ситуацией. На ближайшем совещании было принято решение
внедрить в IT-инфраструктуру компании модуль на базе машинного обучения, способный в реальном
времени оценивать, является ли проводимая транзакция мошеннической. Это, в свою очередь, позволило
бы системе онлайн-платежей отклонить подозрительную операцию.

Вам предлагают принять участие в проектировании и построении такой системы.

В ходе детального обсуждения проекта с представителями заказчика выяснились следующие моменты:

1. Руководство готово выделить на реализацию данного проекта не более 10 млн. руб. (не считая зарплат специалистам).
Через три месяца оно хотело бы увидеть первые результаты, что позволило бы понять, стоит ли дальше развивать проект.
В случае положительного решения, проект нужно завершить за полгода.

2. Из открытых источников известно, что у ближайших конкурентов на каждую сотню проводимых их клиентами транзакций фиксируется
не более двух мошеннических, приводящих к потере денежных средств. При этом общий ущерб клиентов за месяц не превышает 500 тыс. руб.
Разрабатываемая система должна выдавать результаты не хуже, иначе компания станет неконкурентоспособной.

3. В среднем, компания обрабатывает около 50 транзакций в секунду, однако, перед праздниками это число может достигать 400.

4. Если система определит корректную транзакцию как мошенническую, эта транзакция будет отклонена, а пользователь будет недоволен.
Опыт бизнес-аналитиков подсказывает, что если доля таких транзакций превысит 5 %, то начнется отток клиентов из компании.

5. Представители компании не готовы размещать разрабатываемый модуль на собственных вычислительных ресурсах.

6. При проведении транзакции системой вся информация о ней сохраняется в виде csv-файлов, каждая строка которых соответствует одной
транзакции. Информация о транзакциях некоторого фиксированного периода помещается в отдельный файл.

7. Файлы с данными содержат всю информацию о транзакциях, включая данные клиента, который ее проводил. Данная информация является
конфиденциальной, ее утечка недопустима.

## Вам предлагается на основе представленной информации:

1. Сформулировать цели проектируемой антифрод-системы в соответствии с требованиями заказчика.

2. Аргументированно выбрать метрику машинного обучения, оптимизация которой, на Ваш взгляд, позволит достичь поставленных целей.

3. Проанализировать особенности проекта с использованием, например, MISSION Canvas. Это позволит выделить специфику проекта и формализовать
требования к нему, подобрать инструментарий и критерии оценки.

4. Попытаться декомпозировать планируемую систему, определить ее основные функциональные части.

5. Определить задачи, решение которых необходимо для достижения поставленных целей с учетом проведенного анализа. Задачи рекомендуется фор-
мулировать по принципу S.M.A.R.T. На текущий момент, пока не конкретизированы детали антифрод-системы, они могут быть представлены в доста-
точно общем виде. Но они позволят сформировать некоторый roadmap по реализации проекта.

6. Создать GitHub-репозиторий для проекта и разместить в нем сформулированные задачи (∼ 5 задач) на Kanban-доске в GitHub Projects со статусом «Новые».

В дальнейшем, при реализации проекта, эти задачи будут конкретизироваться, дробиться, видоизменяться и выполняться. Их статус
тоже будет изменяться, что позволит Вам наглядно оценивать степень завершенности проекта.

### Анализ задачи и решение
Анализ приведён в файле solution_concept.md

# Домашнее задание No 2

1. Создать новый backet в Yandex Cloud Object Storage и скопировать в него содержимое предоставленного Вам хранилища с использованием ин-
струмента s3cmd. Для проверки преподавателем данный basket необходимо сделать общедоступным, а точку доступа к нему привести в README-файле
Вашего GitHub-репозитория.

2. Создать Spark-кластер в Data Proc с двумя подкластерами со следующими характеристиками:
а) Мастер-подкластер: класс хоста s3-c2-m8, размер хранилища 40 ГБ.
б) Data-подкластер: класс хоста s3-c4-m16, 3 хоста, размер хранилища 128 ГБ.

3. Соединиться по SSH с мастер-узлом и выполнить на нём команду копирования содержимого хранилища в файловую систему HDFS с использовани-
ем инструмента hadoop distcp. Для проверки преподавателем необходимо вывести содержимое HDFS-директории в консоль, а снимок экрана с этой
информацией привести в README-файле Вашего GitHub-репозитория.

4. Пользуясь тарифным калькулятором Yandex Cloud, оценить месячные затраты для поддержания работоспособности созданного кластера.
Оценить, насколько использование HDFS-хранилища дороже, чем объектного.

Указание. Кроме тарифного калькулятора, позволяющего делать оценку требуемых средств, на странице платежного аккаунта есть раздел с детализаци-
ей биллинга за произвольный период времени. С его помощью можно определить сумму уже потраченных средств на каждый из используемых облачных
сервисов в процессе работы.

5. Предложить способы для оптимизации затрат на содержание Spark-кластера в облаке и попробовать их реализовать.

6. В соответствии с достигнутыми результатами, изменить статус ранее созданных задач на Kanban-доске в GitHub Projects.
Возможно, некоторые задачи нужно будет скорректировать, разделить на подзадачи или объединить друг с другом.

7. Полностью удалить созданный кластер, чтобы избежать оплаты ресурсов в период его простаивания.


## Решение

1. s3://mlopss3storage0001/afraud/
2. ![image](https://user-images.githubusercontent.com/25837190/229320080-05c11454-95f6-42c8-a454-8a7a9f93d294.png)
3. 
