# Flume-Kafka-Spark_Streaming
I have implemented a Spark Streaming POC by using Flume to stream data into Kafka and HDFS and use the Kafka topic to publish data to Spark for analysis

First step:
I created a flume agent with a source (log files) and 2 channels and 2 sinks, 1 sink is HDFS and the other sink is the kafka topic. So my Kafka
producer is the flume sink which is being used as one of the destination for log files

