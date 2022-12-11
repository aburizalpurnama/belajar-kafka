# belajar-kafka
Belajar Message Broker Menggunakan Apache Kafka

### Run Kafka

1. Masuk ke direktori kafka
2. Run Zookeeper

        .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

3.  Run Kafka

        .\bin\windows\kafka-server-start.bat .\config\server.properties

### Create topic 

    .\bin\windows\kafka-topics.bat --create --topic contoh-topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 3

notes:
    
- Value --replication harus sesuai dengan jumlah server kafka yang ada.


### Show list of topics

    .\bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092


### Write events to topic

    .\bin\windows\kafka-console-producer.bat --topic quickstart-events --bootstrap-server localhost:9092


### Read events from topic

- From beginning:

        .\bin\windows\kafka-console-consumer.bat --topic quickstart-events --from-beginning --bootstrap-server localhost:9092

- From command executed:

        .\bin\windows\kafka-console-consumer.bat --topic quickstart-events --bootstrap-server localhost:9092

- With consumer group:

        .\bin\windows\kafka-console-consumer.bat --topic contoh-topic --bootstrap-server localhost:9092 --group simple-consumer-app