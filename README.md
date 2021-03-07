# Лабораторна робота №1 студента групи КМ-81 Піткевича Іллі

Перед виконанням програми додайте в корневу папку файли ***Odata2019File.csv***, ***Odata2020File.csv***

## Запуск програми
Для всіх варіантів ОС треба виконати:
```
docker-compose up
```
*Далі запуск відрізняється залежно від системи*
- GNU/Linux
    Для того щоб запустити
    ```
    python3 -m pip install virtualenv
    python3 -m venv env
    source env/bin/activate
    source .env
    python3 -m pip install -r requirements.txt
    python3 main.py
    ```
- Windows OS
    Треба послідовно виконати наступні дії в окремому терміналі
    ```
    py -m pip install --user virtualenv
    py -m venv env
    .\bd_env\Scripts\activate
    py -m pip install -r requirements.txt
    source .env
    py main.py
    ```
*py це execute команда python3, можливо у вас вона відрізняється*

### Індивідуальне завдання

Завдання: `Варіант 7: Порівняти найкращий бал з Математики у 2020 та 2019 роках серед тих комубуло зараховано тест`
Програма виконує запит відповідно до завдання і записує результат у форматі _csv_ в файл `resultQuery.csv`. Результатом
цього запиту э таблиця з 2-ома колонками:

- максимальний бал
- рік
#### Приклад вмісту `resultQuery.csv`
max | year 
--- | --- 
200 | 2019
200 | 2020
### Log

Протягом усієї роботи програма записує свої дії у файл [work_logs.log](./work_logs.log). Також на початку і в
кінці запису даних фіксується час, тому останній запис у цьому файлі — час виконання запису усіх даних з файлів до
таблиць.

## Результати виконання

### Таблиця

#### Перші чотири рядки та стовпці з таблиці ZNO_TABLE

outid|birth|sextypename|regname
--- |--- |--- |--- 
"0000333b-1b93-4386-a148-3d9613bbe324"  |  2002   | "жіноча"  |  "Донецька область"...
"0000333c-efa3-42a7-9f45-e77b53346d57"    | 2002    | "чоловіча"    | "Донецька область"...
"000034f9-ecb8-4e84-bf2e-715d83d79bc8"    | 2003    | "жіноча"    | "Чернігівська область"...
"00003fa1-de6c-488e-a130-8acf4fb817ef"    | 2002    | "жіноча"    | "Сумська область"...

#### Приклад таблиці LastRowTable

year_file | row_num | execute_time
--- | --- | --- 
2020 | 67050 | 191147838

### Logs example

Приклад логів при двох падіннях бази в разних файлах

```
03-07-2021 15:05:29 INFO at row #114 Start time 2021-03-07 15:05:29.337199
03-07-2021 15:05:29 INFO at row #47 Creating table
03-07-2021 15:05:29 INFO at row #67 Tables created
03-07-2021 15:05:29 INFO at row #135 Starting inserting from 0 row from file for 0 year
03-07-2021 15:05:29 INFO at row #72 Inserting data from csv/Odata2019File.csv
03-07-2021 15:06:10 ERROR at row #87 Something went wrong details ->: terminating connection due to administrator command
server closed the connection unexpectedly
	This probably means the server terminated abnormally
	before or while processing the request.

03-07-2021 15:06:16 INFO at row #114 Start time 2021-03-07 15:06:16.660221
03-07-2021 15:06:16 INFO at row #47 Creating table
03-07-2021 15:06:16 ERROR at row #64 relation "lastrowtable" already exists

03-07-2021 15:06:16 INFO at row #67 Tables created
03-07-2021 15:06:16 INFO at row #135 Starting inserting from 140650 row from file for 2019 year
03-07-2021 15:06:16 INFO at row #72 Inserting data from csv/Odata2019File.csv
03-07-2021 15:07:26 INFO at row #109 Inserting from csv/Odata2019File.csv is finished
03-07-2021 15:07:26 INFO at row #72 Inserting data from csv/Odata2020File.csv
03-07-2021 15:07:27 ERROR at row #87 Something went wrong details ->: terminating connection due to administrator command
server closed the connection unexpectedly
	This probably means the server terminated abnormally
	before or while processing the request.

03-07-2021 15:07:42 INFO at row #114 Start time 2021-03-07 15:07:42.447438
03-07-2021 15:07:42 INFO at row #47 Creating table
03-07-2021 15:07:42 ERROR at row #64 relation "lastrowtable" already exists

03-07-2021 15:07:42 INFO at row #67 Tables created
03-07-2021 15:07:42 INFO at row #135 Starting inserting from 3350 row from file for 2020 year
03-07-2021 15:07:42 INFO at row #72 Inserting data from csv/Odata2020File.csv
03-07-2021 15:09:02 ERROR at row #87 Something went wrong details ->: terminating connection due to administrator command
server closed the connection unexpectedly
	This probably means the server terminated abnormally
	before or while processing the request.

03-07-2021 15:09:08 INFO at row #114 Start time 2021-03-07 15:09:08.834189
03-07-2021 15:09:08 INFO at row #47 Creating table
03-07-2021 15:09:08 ERROR at row #64 relation "lastrowtable" already exists

03-07-2021 15:09:08 INFO at row #67 Tables created
03-07-2021 15:09:08 INFO at row #135 Starting inserting from 253800 row from file for 2020 year
03-07-2021 15:09:08 INFO at row #72 Inserting data from csv/Odata2020File.csv
03-07-2021 15:10:01 INFO at row #109 Inserting from csv/Odata2020File.csv is finished
03-07-2021 15:10:01 INFO at row #43 COPY TO CSV SUCCESSFUL
03-07-2021 15:10:01 INFO at row #155 End time 2021-03-07 15:10:01.728319
03-07-2021 15:10:01 INFO at row #156 Inserting executing time 0:03:56.844750
03-07-2021 15:10:01 INFO at row #159 Program is finished
```
***Як видно час на виконання достатньо швидкий, імпортувалося 733112 рядків, тобто 100% csv файлу***
