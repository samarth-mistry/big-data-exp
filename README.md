# big-data-exp
Experiment and learning big data technology, Hadoop, Spark, PySpark, SparkSQL

# https://developer.confluent.io/quickstart/kafka-docker/
## list topic
docker exec broker kafka-topics --bootstrap-server broker:9092 --list
## create a topic
docker exec broker kafka-topics --bootstrap-server broker:9092 --create --topic quickstart
## write to topic
docker exec --interactive --tty kafka_spark_streaming_kafka_1 kafka-console-producer --bootstrap-server kafka_spark_streaming_kafka_1:9092 --topic quickstart
## Read messages from the topic
docker exec --interactive --tty kafka_spark_streaming_kafka_1 kafka-console-consumer --bootstrap-server kafka_spark_streaming_kafka_1:9092 --topic quickstart --from-beginning
## describe topic 
docker exec kafka_spark_streaming_kafka_1 kafka-topics --bootstrap-server kafka_spark_streaming_kafka_1:9092 --describe --topic quickstart
## list consumers
docker exec kafka_spark_streaming_kafka_1 kafka-consumer-groups --list --bootstrap-server kafka_spark_streaming_kafka_1:9092
## describe consumers
docker exec kafka_spark_streaming_kafka_1 kafka-consumer-groups --bootstrap-server kafka_spark_streaming_kafka_1:9092 --describe --group console-consumer-4666
## KOWL
docker run -d -p 8080:8080 -e KAFKA_BROKERS=localhost:9092 quay.io/cloudhut/kowl:master
