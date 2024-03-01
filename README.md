In the bin directory, you can start using the Kafka command-line

To create a topic:

./kafka-topics.sh --create --topic my-topic --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1

List the topics:
./kafka-topics.sh --list --bootstrap-server localhost:9092

To start a producer console:
./kafka-console-producer.sh --broker-list localhost:9092 --topic my-topic

To start  a consumer console (printing to stdout):
./kafka-console-consumer.sh --bootstrap-server localhost:9092 --from-beginning --topic my-topic --formatter kafka.log.LogMessageFormatter

//Here <topic_name> = weather : Adjust accordingly
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic weather --from-beginning --max-messages 10


You will see something like this if everything is working correctly:
Topic weather has received your message. Delivery Successful | Offset 120001
Topic weather has received your message. Delivery Successful | Offset 120002
Topic weather has received your message. Delivery Successful | Offset 120003
...

