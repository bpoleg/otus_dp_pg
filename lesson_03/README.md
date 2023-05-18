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

## Вторая часть ДЗ

- подключился к виртуальной машине 
  установил постгресс:
  sudo apt update && sudo apt upgrade -y && sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list' && wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add - && sudo apt-get update && sudo apt-get -y install postgresql-15
  
- создал БД example
- установил на эту бд таблицы pgbench
  ![установка](../picture/lesson_04/p01.png)
- проверил производительность с установками по умолчанию
  ![производительность](../picture/lesson_04/p02.png)
  ![мониторинг](../picture/lesson_04/p03.png)
  592 транзакции в секунду
- увеличил вдвое shared Buffers
  ![производительность](../picture/lesson_04/p04.png)
  ![мониторинг](../picture/lesson_04/p05.png)
  754 транзакции в секунду
- установил shared Buffers в 1/3 свободной памяти
  ![узнал свободную память](../picture/lesson_04/p06.png)
  ![установил shared Buffers](../picture/lesson_04/p07.png)
  ![производительность](../picture/lesson_04/p08.png)
  1191 транзакция в секунду
- увеличил количество коннекций
  ![увеличил количество коннекций](../picture/lesson_04/p09.png)
  ![производительность](../picture/lesson_04/p10.png)
  1520 транзакций в секунду
- увеличил количество коннекций
  ![увеличил количество коннекций](../picture/lesson_04/p11.png)
  ![производительность](../picture/lesson_04/p12.png)
  1670 транзакций в секунду
- изменил work_mem
  ![увеличил количество коннекций](../picture/lesson_04/p13.png)
  ![мониторинг](../picture/lesson_04/p14.png)
  ![производительность](../picture/lesson_04/p15.png)
  1191 транзакций в секунду

- изменил work_mem
  ![увеличил количество коннекций](../picture/lesson_04/p16.png)
  ![производительность](../picture/lesson_04/p17.png)
  1319 транзакций в секунду
- изменил work_mem
  ![увеличил количество коннекций](../picture/lesson_04/p18.png)
  ![производительность](../picture/lesson_04/p19.png)
  1449 транзакций в секунду


Машину после использования положил
