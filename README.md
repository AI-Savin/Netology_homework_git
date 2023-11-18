# Домашнее задание к занятию "`8-02_Система_мониторинга_Zabbix`" - `Savin Aleksey`

### Задание 1
Установите Zabbix Server с веб-интерфейсом.

***Процесс выполнения***
1. Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
2. Установите PostgreSQL. Для установки достаточна та версия, что есть в системном репозитороии Debian 11.
3. Пользуясь конфигуратором команд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache.
4. Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server.
   
***Требования к результату***

1. Прикрепите в файл README.md скриншот авторизации в админке.
2. Приложите в файл README.md текст использованных команд в GitHub.


### Решение 1
![zabbix](https://github.com/AI-Savin/Netology_hw_8.02/blob/main/img/zabbix.png)  

 **команды**  
 
 `sudo apt install postgresql`  
 `wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-5+debian12_all.deb`   
 `sudo dpkg -i zabbix-release_6.0-5+debian12_all.deb`  
 `sudo apt update`  
 `sudo apt install zabbix-server-pgsql zabbix-frontend-php php8.2-pgsql zabbix-apache-conf zabbix-sql-scripts`  
 `sudo -u postgres createuser --pwprompt zabbix`  
 `sudo -u postgres createdb -O zabbix zabbix`  
 `zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix`  
 `sudo nano /etc/zabbix/zabbix_server.conf`  
 `sudo systemctl restart zabbix-server apache2`  
 `sudo systemctl enable zabbix-server apache2`  
 
---

### Задание 2
Установите Zabbix Agent на два хоста.

***Процесс выполнения***
1. Выполняя ДЗ, сверяйтесь с процессом отражённым в записи лекции.
2. Установите Zabbix Agent на 2 вирт.машины, одной из них может быть ваш Zabbix Server.
3. Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов.
4. Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera.
5. Проверьте, что в разделе Latest Data начали появляться данные с добавленных агентов.
   
***Требования к результату***  

1. Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
2. Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
3. Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
4. Приложите в файл README.md текст использованных команд в GitHub 

### Решение 2
[**ссылка на коммит .gitignore**](https://github.com/AI-Savin/first_github/commit/21ff6a2e7932e2be65023e9c84102a572bfd6fed)

---

### Задание 3

**Что нужно сделать:**

1. Создайте новую ветку dev и переключитесь на неё.
2. Создайте в ветке dev файл test.sh с произвольным содержимым.
3. Сделайте несколько коммитов и пушей в ветку dev, имитируя активную работу над файлом в процессе разработки.
4. Переключитесь на основную ветку.
5. Добавьте файл main.sh в основной ветке с произвольным содержимым, сделайте комит и пуш . Так имитируется продолжение общекомандной разработки в основной ветке во время разработки отдельного функционала в dev ветке.
6. Сделайте мердж dev ветки в основную с помощью `git merge dev`. Напишите осмысленное сообщение в появившееся окно комита.
7. Сделайте пуш в основной ветке.
8. Не удаляйте ветку dev.
В качестве ответа прикрепите ссылку на граф коммитов https://github.com/ваш-логин/ваш-репозиторий/network в ваш md-файл с решением.

Ваш граф комитов должен выглядеть аналогично скриншоту:

![скрин для Git](https://github.com/netology-code/sdvps-homeworks/assets/77622076/e73589cf-7e97-40e5-ac01-d1d55376f1b9)  


### Решение 3

[**ссылка на график коммитов**](https://github.com/AI-Savin/first_github/network)
