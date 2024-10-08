# Домашнее задание к занятию "`Работа с данными (DDL/DML)`" - `Маркин Алексей`

### Задание 1

1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp. 

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

1.4. Дайте все права для пользователя sys_temp. 

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос: 
```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

*Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.*

---

### Решение 1

1.2. CREATE USER 'sys_temp'@'%' IDENTIFIED BY 'sys_temp';

1.3. 
![Задание 1.3] (https://github.com/Markin-AI/12-2/blob/main/img/1-3.png)

1.4. GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'%' WITH GRANT OPTION;

1.5. 
![Задание 1.5] (https://github.com/Markin-AI/12-2/blob/main/img/1-5.png)

1.6. 
![Задание 1.6] (https://github.com/Markin-AI/12-2/blob/main/img/1-6.png)

1.7. docker exec -it c169bdff6983 mysql -uroot -p
	 create database sakila;
	 use sakila;
	 source /var/lib/mysql/sakila-schema.sql;
	 source /var/lib/mysql/sakila-data.sql;

1.8 
![Задание 1.8] (https://github.com/Markin-AI/12-2/blob/main/img/1-8.png)

![Задание 1.8] (https://github.com/Markin-AI/12-2/blob/main/img/1-8_2.png)

---

### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)
```
Название таблицы | Название первичного ключа
customer         | customer_id
```

---

### Решение2

![Задание 2](https://github.com/Markin-AI/12-2/blob/main/img/2-1.png)

---