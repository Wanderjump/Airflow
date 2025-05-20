# Установка Airflow

## Активация wsl. Должно быть установлено wsl
```bash
wsl -u root # активация wsl с правами пользователя
```
## Создание нового вирт.окр. и активация
```bash
cd C:\
mkdir Airflow 
cd Airflow
python3 -m venv airflow_venv
source airflow_venv/bin/activate
```

## Обновите пакетный менеджер

   Убедитесь, что ваш пакетный менеджер обновлен:

   ```bash
   sudo apt update
   sudo apt upgrade
   ```

## Установите необходимые зависимости

   Установите зависимости, необходимые для работы Airflow:

   ```bash
   # Для Postgres
   sudo apt install -y python3-pip python3-dev libpq-dev build-essential
   # Для MySQL
   sudo apt install -y python3-pip python3-dev libmysqlclient-dev build-essential
   ``` 

## Установите Apache Airflow

   Установите Airflow с использованием `pip`. Вы можете указать версию и дополнительные зависимости:
   ```bash
   pip install apache-airflow
   ```
   Если вы хотите установить Airflow с поддержкой определенных провайдеров, вы можете использовать:
   ```bash
   pip install apache-airflow[postgres,google]
   ```
   (замените `postgres,google` на нужные вам провайдеры).

## Проверьте установку

   После завершения установки проверьте, что Airflow установлен:

   ```bash
   pip show apache-airflow
   ```

## Инициализируйте базу данных

   Перед запуском Airflow необходимо инициализировать базу данных:

   ```bash
   airflow db init
   ```
**Для использования Postgres необходимо ее настроить**
**Создайте нового пользователя**
```bash
airflow users create \
    --username new_user \
    --firstname FirstName \
    --lastname LastName \
    --role Admin \
    --email user@example.com
    ```

**Запустите Airflow**:

   Теперь вы можете запустить Airflow:

   ```bash
   airflow scheduler & airflow webserver -p 8080
   ```









