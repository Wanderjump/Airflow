### ***Работа с Airflow через wsl и виртуальное окружение***
1. Актирировать wsl. 
`wsl -u root`
2. Акривировать окружение: 
2.1. Перейти в папку где находится окружение
`cd /path/to/venv`
2.2. Запустить окружение
`source name_of_venv/bin/activate`
3. Запустить airflow:
`airflow scheduler & airflow webserver -p 8080`
4. Выход из Airflow Ctrl + C
5. Деактивация виртуального окружения
`deactivate`
6. Выход из wsl - `exit`

### ***Работа с БД***
1. Просмотр базы данных:
Для MySQL:
`mysql -u Airflow -p -h localhost -P 33061`
Для PostgresQL:
`psql -h 127.0.0.1 -U postgres -d airflow`
2. Просмотр баз данных: можно пропустить
MySQL: SHOW DATABASES;
PSQL: \l
3. Просмотр таблиц: можно пропустить
MySQL: SHOW TABLES; 
PSQL: \dt 
4. Использовать БД:
MySQL: `USE database;` Указываем название базы данных
PSQL: \c имя_базы_данных
5. `SELECT * FROM table;` Указываем нужную таблицу
6. Выход из sql - `exit`