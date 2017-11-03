# Flume-Kafka-Spark_Streaming
I have implemented a Spark Streaming POC by using Flume to stream data into Kafka and HDFS and use the Kafka topic to publish data to Spark for analysis

First step:
I created a kafka topic with rplication 2 and 2 partitions to store ths data

Second step:
I created a flume agent with a source (log files) and 2 channels and 2 sinks, 1 sink is HDFS and the other sink is the kafka topic. So my Kafka producer is the flume sink which is being used as one of the destination for log files

Third step:
To test whether the fulme agent is running or not and kafka topic is recieving messages or not I initiated a kafka consumer
which is publishing my log files

Last step:
After writing the Spark Streaming module in Scala, I generated the jar file by moving to the location of the SparkStreaming
project in command prompt and ran the sbt package command which generated the jar file. Now the jar file is shipped to cluster to execute the Spark Streaming module by using the command spark-submit --class StreamingDepartmentAnalysis   --master yarn   --conf spark.ui.port=22231   --jars "/usr/hdp/2.5.0.0-1245/spark/lib/spark-streaming_2.10-1.6.2.jar,/usr/hdp/2.5.0.0-1245/kafka/libs/spark-streaming-kafka_2.10-1.6.2.jar,/usr/hdp/2.5.0.0-1245/kafka/libs/kafka_2.10-0.8.2.1.jar,/usr/hdp/2.5.0.0-1245/kafka/libs/metrics-core-2.2.0.jar" sparkstreaming_2.10-1.0.jar /user/rss161030/Streaming_Output/

We get the desired results in the form of HDFS files

