# belajar-kafka
Belajar Message Broker Menggunakan Apache Kafka

## Kafka + GO (confluent)

### 1. Get Kafka library

    go get github.com/confluentinc/confluent-kafka-go/kafka

### 2. Create docker-compose.yml

### 3. Run docker compose
        
    docker compose up -d

### 5. Create topic

    docker compose exec broker kafka-topics --create --topic purchases --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1

### 6. Create & build Producer

    go build -o out/producer.exe util.go producer.go

### 7. Create & build Consumer

    go build -o out/consumer.exe util.go consumer.go

### 8. Run Producer

    .\out\producer.exe getting-started.properties

### 9. Run Consumer

    .\out\consumer.exe getting-started.properties

## Belajar Menggunakan Console
### Run Kafka

1. Masuk ke direktori kafka
2. Setting zookeeper (config\zookeeper.properties)
3. Setting kafka (config\server.properties)
Untuk windows, saat mendeklarasikan path harus seperti ini: (D:\\rizal\\data\\kafka)

4. Run Zookeeper

        .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

5.  Run Kafka

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