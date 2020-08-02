Zabbix-server 5.0
=========

Роль предназначена для установки и конфигурирования zabbix-server и zabbix-frontend  

Роль __не предоставляет__ возможность установки СУБД


Компоненты роли
--------------
__Роль состоит из следующих playbooks:__  

1. main.yml - установка и настройка Zabbix-server  
2. zabbix-frontend.yml - установка и настройка Zabbix-frontend  
3. zabbix-frontend-ssl.yml - playbook вызывается если необходимо настроить SSL сертификаты для web-сервера (  zabbix_frontend_ssl|int > 0 )   

Описание переменных
--------------

__zabbix_server_version__ - версия Zabix-server  

__zabbix_repo_url__ - репозиторий для установки Zabix-server    

__zabbix_non_supported_repo__ - репозиторий для дополнительных пакетов необходимых для корректной установки Zabbix-server  

__zabbix_server_database__ - СУБД которая будет использоваться для работы с Zabix-server ( mysql | pgsql )

__zabbix_web_server__ - web-сервер для Zabbix-frontend ( apache | nginx )

__zabbix_server_db_name__ - имя БД Zabbix

__zabbix_server_db_user__ - пользователь для работы с Zabbix БД  

__zabbix_server_db_password__ - пароль пользователя для работы с Zabbix БД 

__zabbix_server_db_host__ - адрес хоста на котором расположена БД Zabbix  

__zabbix_server_db_port__ - TCP-порт для обращений к СУБД в котором располагается БД Zabbix 

__zabbix_alertscripts_dir__ - директория в которой хранятся скрипты оповещения  

__zabbix_frontend_ssl__ - использовать SSL сертификаты в Zabbix-frontend ( 0 | 1)  

__zabbix_frontend_ssl_certificate_dir__ - директория в которой будет располагаться SSL сертификат  

__zabbix_frontend_ssl_key_dir__ - директория в которой будет располагаться SSL ключ    

__zabbix_frontend_ssl_certificate__ - переменная используется для деплоя SSL сертификата на хост (если переменная не определена, то playbook zabbix-frontend-ssl.yml не будет вызван)  

__zabbix_frontend_ssl_key__ - переменная используется для деплоя SSL ключа на хост (если переменная не определена, то playbook zabbix-frontend-ssl.yml не будет вызван)  

__zabbix_server_conf__ - переменная используется для деплоя конфигурации zabbix на хост  

__zabbix_web_conf__ - переменная используется для деплоя конфигурации zabbix-frontend на хост  

__zabbix_nginx_conf__ - переменная используется для деплоя конфигурации rh-nginx116-nginx на хост (используется если nginx выбран в качестве web-сервера)

__zabbix_apache_conf__ - переменная используется для деплоя конфигурации apache на хост (используется если apache выбран в качестве web-сервера)  

__zabbix_apache_ssl_conf__ - переменная используется для деплоя конфигурации apache ssl mod на хост (используется если apache выбран в качестве web-сервера и используется SSL шифрование)  

__zabbix_php_fpm_conf__ - переменная используется для деплоя конфигурации php-fpm на хост  

__zabbix_alertscripts__ - переменная используется для деплоя скриптов оповещения на хост  
 
__zabbix_server_state__ - статус сервиса zabbix-server ( "reloaded", "restarted", "started", "stopped" ) 

__zabbix_server_enabled__ - добавить ли процесс zabbix-server в автозагрузку ("true", "false")

__zabbix_frontend_state__ - статус сервиса zabbix-frontend ( "reloaded", "restarted", "started", "stopped" )   

__zabbix_server_enabled__ - добавить ли процессы zabbix-frontend в автозагрузку ("true", "false")