# Kafka Performance Testing

How to performance test Kafka ?

Apache kafka provides two inbuilt tools 
1. Kafka-Producer-Performance-test.sh
     This is to produce messages into a topic on the broker(s)
2. Kafka-consumer-perf-test.sh
     This is to consume the messages from the kafka topics

**High Level**
1. Download Apache kafka
2. Start Zookeeper
3. Start Kafka Server
4. Run Kafka-Producer-Performance-test.sh

**Detailed Steps**
1. Download Apache kafka: curl "https://downloads.apache.org/kafka/3.7.0/kafka_2.12-3.7.0.tgz" -o <filename>.tgz
2. uncompress the compressed file: tar -xvzf <filename>.tgz
3. Set path: export path="${PATH}:/<filepath>/bin"
4. Start zookeeper: zookeeper-server-start.sh /kafkafolderpath/config/zookeeper.properties
5. Start Kafka server: kafka-server-start.sh /kafkafolderpath/config/server.properties
   
**How to produce Kafka messages into broker**

kafka-producer-perf-test.sh --topic <topicname> --num-records Anynumber --throughput Any_number --producer-props bootstrap.servers=BrokerIPAddress --record-size size_in_bytes

e.g kafka-producer-perf-test.sh --topic abcd --num-records 10000 --throughput 50 --producer-props bootstrap.servers=11.111.111.11:9092,11.111.111.12:9092 --record-size 150
