# Flume-Kafka-Spark_Streaming
I have implemented a Spark Streaming POC by using Flume to stream data into Kafka and HDFS and use the Kafka topic to publish data to Spark for analysis

First step:
I created a flume agent with a source (log files) and 2 channels and 2 sinks, 1 sink is HDFS and the other sink is the kafka topic. So my Kafka
producer is the flume sink which is being used as one of the destination for log files

Second step:
To test whether the fulme agent is running or not and kafka topic is recieving messages or not I initiated a kafka consumer
which is publishing my log files

Third step:
After writing the Spark Streaming module in Scala, I generated the jar file by moving to the location of the SparkSpreaming
project in command prompt and ran the sbt package command which generated the jar file. Now the jar file can be shipped to cluster to execute the Spark Streaming module.

