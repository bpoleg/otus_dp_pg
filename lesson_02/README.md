# otus_dp_pg
урок по проверке уровней транзакции

# Создание виртуальной машины
- зашел на console.cloud.yandex.ru
- создал платежный аккаунт
- привязал к нему  виртуальную карту
- создал виртуальную машину. 
- для связи использовал сгенерированный rsa ключ
машина создалась для убунты 22
  ssh -i ~/.ssh/yc_key otus@158.160.29.167
- ![тест1 ](../picture/lesson_01/p0.png)

## Установка Docker

- подключился к виртуальной машине 
  выполнил:
  sudo apt update
  sudo apt install curl software-properties-common ca-certificates apt-transport-https -y
  curl -f -s -S -L https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu jammy stable"
  apt-cache policy docker-ce

  ![статус докера](../picture/lesson_02/p01.png)
## Установка в докер постгресс
- ![Установка постгресса в доккер](../picture/lesson_02/p02.png)
### Создал папку /var/lib/postgres
   sudo mkdir -p /var/lib/postgres
   Важно! папка должна иметь хозяина lxd иначе докер не может смапировать
### развернул контейнер с PostgreSQL 14 смонтировав в него /var/lib/postgres
- ![старт контейнера](../picture/lesson_02/p03.png)
### подключился с контейнеру с локальной машины.
- ![описание подключения](../picture/lesson_02/p04.png)
### проверка соединения.
- ![результат теста соединения](../picture/lesson_02/p05.png)
### создал тестовую таблицу.
- ![тестовая талица с тестовыми данными](../picture/lesson_02/p06.png)
### список запущенных контейнеров.
- ![контейнеры](../picture/lesson_02/p07.png)
### остановил и удалил контейнер.
- ![удалил контейнер](../picture/lesson_02/p08.png)
### стартовал контейнер смонтировав в него  /var/lib/postgres
- ![удалил контейнер](../picture/lesson_02/p09.png)
### подключился с контейнеру с локальной машины.
- ![данные на месте](../picture/lesson_02/p10.png)

Машину после использования положил
