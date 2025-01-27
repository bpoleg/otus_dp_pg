# otus_kafka
урок по самостоятельному развертыванию кафки

# Создание виртуальной машины
машина создалась для убунты 22
ssh -i ~/.ssh/yc_key otus@158.160.29.167
- ![тест1 ](../picture/lesson_01/p00.png)
- выполняю  
  1. sudo apt update
  2. sudo apt upgrade
  3. sudo apt install default-jre
  4. sudo apt install default-jdk
  5. wget https://downloads.apache.org/kafka/3.7.2/kafka_2.13-3.7.2.tgz
  6. tar xzf kafka_2.13-3.7.0.tgz
  7. cd kafka_2.13-3.7.2
  8. ./bin/zookeeper-server-start.sh config/zookeeper.properties
  9. в новой коннекции
  cd kafka_2.13-3.7.2
  10. ./bin/kafka-server-start.sh config/server.properties
  11. в новой коннекции
- проверил список топиков
  ./bin/kafka-topics.sh --list --bootstrap-server localhost:9092
 ![тест1 ](../picture/lesson_01/p01.png)
- создал топик 
./bin/kafka-topics.sh --create --topic topic1 --bootstrap-server localhost:9092
![тест1 ](../picture/lesson_01/p02.png)
- проверка записи и чтения в топики
  ![тест1 ](../picture/lesson_01/p03.png)
