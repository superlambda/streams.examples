1: To test Pipe
bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/server.properties
bin/kafka-topics.sh --create \
 --bootstrap-server localhost:9092 \
              --replication-factor 1 \
 --partitions 1 \
 --topic streams-plaintext-input
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 \
 --topic streams-pipe-output  \    
 --from-beginning 
add some test in the producer

2: To test LineSplit
bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/server.properties
bin/kafka-topics.sh --create \
 --bootstrap-server localhost:9092 \
              --replication-factor 1 \
 --partitions 1 \
 --topic streams-plaintext-input
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 \
 --topic streams-linesplit-output  \    
 --from-beginning 
add some test in the producer

3: To test WordCount
bin/zookeeper-server-start.sh config/zookeeper.properties
bin/kafka-server-start.sh config/server.properties
bin/kafka-topics.sh --create \
--bootstrap-server localhost:9092 \
--replication-factor 1 \
--partitions 1 \
--topic streams-plaintext-input
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 \
	--topic streams-wordcount-output \
--from-beginning \
--formatter kafka.tools.DefaultMessageFormatter \
--property print.key=true \
--property print.value=true \
--property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer\
             --property
value.deserializer=org.apache.kafka.common.serialization.LongDeserializer
add some test in the producer

