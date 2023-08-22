# LPM-client

[Серверная часть](https://github.com/Lumetas/LPM-server)

Lum Project Manager - небольшое клиент-серверное приложение для управления вашими проектами№.

## Установка

Поскольку клиентская часть представляет собой bash скрипт то установки он не требует можете просто закинуть его в "/usr/bin". 

Например так:
~~~
wget "https://raw.githubusercontent.com/Lumetas/LPM-client/main/lpm"; chmod +x lpm; sudo mv lpm /usr/bin
~~~

## Оформление конфигурационного файла(lumake).
~~~
project
localhost:8000
echo init
echo run
echo build
1.0
~~~
1. Имя проекта(желательно на латинице, без пробелов и спец.символов).

2. Aдресс сервера с которым будет связан проект

3-5. shell-команды для инициализации, запуска и сборки соответственно

6. Версия проекта

## Использование 

Находясь в корне вашего проекта, создав и оформив lumake файл. Используйте:

lpm commit - Чтобы загрузить проект на сервер

lpm get - Чтобы заменить локальную версию проекта на версию проекта с сервера

lpm [init, run, build] - Для выполнения команд инициализации, запуска и сборки соответственно

Так же серверные функции. Они имеют другой синтаксис и не обязаны использоваться в папке проекта. Синтаксис:
~~~
lpm server example.com:8000 command lumproj
~~~
Команды: 

clone - Создаёт папку в которую скачивает проект с сервера

version - Выводит версию проекта на сервере

remove - удаляет проект с сервера

init, run, build - выполняют соответствующие команды из папки проекта на сервере. Транслирует вывод из этих команд.

### После использования любой из команд вас попросят указать пароль сервера читать в readme серверной части: [Серверная часть](https://github.com/Lumetas/LPM-server)
