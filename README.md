# [WIP] Лабораторные работы за осенний семестр 2020

В `master` ветке данного репозитория присутствуют актуальные задания, включая 
распределение протоколов по студентам.

## Lab 1

Данная работа нацелена на реализацию чата.
Разрабатывается серверная и клиентская части.

Требования к чату:

* Возможность подключения нескольких клиентов к одному чату;
* Отображение отправленного сообщения у каждого подключенного в этот
момент к серверу клиента.

Требования к реализации:

* Самостоятельное использование TCP сокетов

Реализация хранения и отображения истории **не обязательно**.
Используемый язык программирования - **на выбор студента** (никаких ограничений)

Формат сообщения желателен следующий:

```
<HH:MM> [username] Text of an actual message
```

Пример сообщения:

```
<4:20> [Kenobi] Hello there!
```

Требования к отчету:

* Инструкция по использованию;
* Инструкция по сборке/установке;
* Описание используемого протокола.

Отчет можно писать как в сообщении к MR-у, так и присылать в иных 
форматах (`.pdf`, `.docx`, `.txt` и т.п.).

## Lab 2

Для изменения/назначения своих сервера и клиента можно написать в чат своей группы по данному предмету или завести отдельный PR с изменением нижеприведённой таблицы.

### Группа 203

| Студент     | Сервер | Клиент |
| --          | --     | --     |
| Трушин Иван | tftp   | dhcp   |
| Шелепов     | dhcp   | tftp   |
| Меньшов     | dns    | tftp   |
| Морозов     | dns    | dhcp   |
| Орлова      | tftp   | dns    |
| Семёнов     | dhcp   | dns    |
| Калашников  | dns    | snmp   |
| Костарев    | dhcp   | snmp   |
| Середин     | dhcp   | ntp    |


## Lab 3

