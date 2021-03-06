# project_3
## Building a real-time data streaming application with Apache Kafka
### Project Description

* Real-Time Meetup RSPV Data Processing from https://www.meetup.com/. Real-Time Analytics using Apache Kafka, Zookeeper, Py Spark. Analyzing the real time RSVP data of meetup.com to get real-time insights such as trending topics, cities etc. along with other business insights related to Meetups RSVPs. The data processing scripts are developed in Python.
### Technologies Used
*  Python 3.6
*  Kafka 2.8.0
*  Spark 3.1.2
*  Pyspark 2.4.8
*  Git/GitHub
*  kafka-python 2.0.2
*  Kafka Python API is used to interact with kafka cluster. PySpark is used to write the spark streaming jobs

### problem statements
*  What are the current active cities in US which are scheduling Meetup Events?
*  What are the trending topics in US Meetup Events?
### Execute the Application
* Assuming Kafka and Spark of appropriate version is installed, the following commands are used to run the application.

Spark Streaming integeration with kafka 0.10.0.0 and above, is still in experimental status, Hence using Kafka 0.9 (http://spark.apache.org/docs/latest/streaming-kafka-integration.html)

Run Zookeeper to maintain Kafka, command to be run from Kafka root dir bin/zookeeper-server-start.sh config/zookeeper.properties1

Start Kafka server, aditional servers can be added as per requirement. bin/kafka-server-start.sh config/server.properties

Start Producer.py to start reading data from the meetup stream and store it in '''meetup''' kafka topic.

Start Consumer.py to consume the stream from the '''meetup''' topic

Submit the spark job spark_meetup.py, to read the data into Spark Streaming from Kafka.

Spark depends on a external package for kafka integeration link

bin/spark-submit --packages org.apache.spark:spark-streaming-kafka-0-8_2.11:2.0.1 spark_meetup.py localhost:2181 meetup An analysis of number of RSVPs from various cities in "US" region is performed on the RSVPs Stream.
 ### License
* This project uses the following license: MIT License
### References
https://mvnrepository.com/artifact/org.apache.spark/spark-streaming-kafka-0-8_2.11/2.0.1)
