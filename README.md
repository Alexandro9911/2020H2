# Лабораторная N 1а
 
Создание TCP чата на блокирующих сокетах

## Инструкция по использованию.

Клиент и сервер написаны на Java, по этому на тестируемом компьютере должна быть установлена Java-машина. 

1 вариант запуска: запустить исходные Jar файлы(сейчас должны работать) 

Сначала запускается сервер: 

  java -jar [path] Server.jar  
  
  потом ввести порт сервера и нажать Enter 

jar файл сервера находится в Server/out/artifacts/Server_jar/Server.jar 

Далее запускается клиент:

java -jar [path] Client.jar
  
потом ввести порт сервера и нажать Enter а далее ввести имя пользователя

jar файл клиента находится в Client/out/artifacts/Client_jar/Client.jar

2 вариант запуска: собрать и запустить. См. раздел сборки.

Когда клиент подключится к серверу, сервер у себя в консоле напишел о подключении клиента и у клиента появятся изменения.
При потере соединения клиента и сервера  клиент выводит соответственное сообщение о потере соединения и со временем клиент закрывается. 

Остановить сервер:  в консоль сервера написать stop server
Остановить клиент:  в консоль клиента написать close chat 

Клиент не запустится если не запущен сервер. Клиент выведет сообщение о том что нет соединения с сервером.

При подключении нового клиента показывается сообщение, оповещающее что клиент вошел в чат, а так же при разрыве соединения, показывается, какой клиент покинул чат.

## Инструкция по сборке

Сервер:
компилируем

javac -sourcepath ./src -d bin src/com/alexandr/server/Main.java 

На выходе команды получаем бинарники и его можно запустить

запускаем 
java -classpath ./bin com/alexandr/server/Server

Клиент:
компилируем

javac -sourcepath ./src -d bin src/com/alexandr/client/Main.java 

запускаем 
java -classpath ./bin com/alexandr/client/Client

## Протокол

Пакет имеет вид: 

[длина времени][длина имени][длина сообщения][время][имя][сообщение]
пример:

Есть сообщение: 12:03:11 Alex Hello there

получится такой пакет:
[8][4][11][время в байтах][имя в байтах][сообщение в байтах]
Первые три поля - размером в байт - являются неким заголовком, остальные три поля - сами данные. 
Если сообщение слишком длинное  - сообщение обрежется по размерам. 
Если длинное имя или нулевое -  клиент не запустится. 

## Для отправки сообщения:

Написать в консоль сообщение и нажать enter.  сообщение отправлено. на сообщение накладывается ограничение длины в 2048 байта, что обусловлено размерами буффера на сервере
а так же максимальная длина ника составляет 16. Это обусловлено в эстетических целях, так как большое имя не удобно к восприятию.
Пустое сообщение не отправится. 

Если клиент попытается зайти под уже существующим ником, сервер сбросит это соединение и клиент выведет соответствующее сообщение.

## Время отправки сообщения: 
Время когда было отправлено сообщение определяется при отправке сообщения и отправляется на сервер. Далее, время рассылается всем пользователям вместе с конкретным сообщением и отображается рядом с сообщением. 
 

