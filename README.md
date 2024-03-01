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
[2016-05-31 14:38:37,177] INFO Registered kafka:type=producer,host=localhost,port=49156
[2016-05-   31 14:38:37,182] INFO Created topic my-topic with 1 partition(s), replication factor 1 and 1 brokers in cluster.    
[2016-05-31 14:38:37,183] INFO Produced message to topic my-topic partition 0 at offset  0
[2016-05-   31 14:38:38,188] INFO Produced message to topic my-topic partition 0 at offset  1
...

In another terminal window, run the consumer again but with --from-file instead of --from-beginning and provide it with the filename
In another terminal window, run the consumer again but with `--from-file` instead of `--from-beginning`. This time it should print out
In another terminal window, run the consumer again but with --from-file instead of --from-beginning and provide it with a file containing some