# Homework 1

## Установка MongoDB

1. Найдена документация по установке
2. Выполнены все представленные команды по установке MongoDB на локальный компьютер с ОС Ubuntu 22.04

![Alt text](./img/1.png "MongoDB Version")

## Создание и заполнение БД

1. Запущен процесс mongod через команду: sudo systemctl start mongod
2. Командой 'sudo systemctl status mongod' была проверена успешность запуска сервера
3. Запущена сессия командой 'mongosh'. Предварительно был удален файл /tmp/mongodb-27017.txt и перезапущен сервер для устранения ошибки 'connect ECONNREFUSED 127.0.0.1:27017'
4. Создана таблица командой db.createCollection("titanic") и выведена некоторая статистика
5. Скачан датасет titanic (train-часть). Командой 'mongoimport -d hw1 -c titanic --type csv --file data/titanic_train.csv --headerline' данные с файла были импотированы в hw1.titanic
6. Было выведено количество документов в коллекции и документ с passengerId = 5

![Alt text](./img/2.png "Check creation")

## CRUD-операции
 
1. На следующем скриншоте показано несколько операций вставок с помощью insertOne() и insertMany() (create)

![Alt text](./img/3.png "Check creation")

2. На следующих скриншотах показана пара комплексных запросов find (read)

![Alt text](./img/4.png "Check reading")
![Alt text](./img/5.png "Check reading")

3. На следующем скриншоте показаны операции обновления одного и нескольких объектов (update)

![Alt text](./img/6.png "Check updating")

4. На следующем скриншоте показаны операции удаления одного и нескольких объектов (delete)

![Alt text](./img/7.png "Check Deleting")

## Индексирование

1. Для оценки индексов был выбран запрос, группирующий данные по полям Pclass и Survived, рассчитывающий средний возраст в каждой группе. Для оценки производительности дополнительно вызывается команда .explain("executionStats") и оценивается поле executionTimeMillis

![Alt text](./img/8.png "Without index")

executionTimeMillis = 18

2. Создаем композитный индекс для полей Pclass и Survived, выполняем тот же запрос и заново оцениваем производительность

![Alt text](./img/9.png "Without index")

executionTimeMillis = 1

