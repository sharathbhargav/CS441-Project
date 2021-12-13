# Build Streaming Pipeline using Akka, Kafka and Spark. 

## **_Course Project_**
This was our course project for CS 441 taken under the guidance of Prof. Mark Grechanik. 

**_Project Members_**

| Name | UIN |
| :---: | :---: |
|Aditya Kanthale | 663141759|
| Parth Deshpande | 657711378 |
| Jeet Mehta | 668581235
| Sharath Bhargav | 663652557
| Harsh Mishra | 653554247

## Overview:

In this project we have created a streaming data pipeline using various cloud technologies alongside implementing an actor-model such as Akka that helped us ingesting the log file which is generated in real time. This file is delivered via an event-based service called Kafka and sent to Spark for further processing. In the Spark pipeline aggregations are performed for the log type `WARN` and `ERROR` that sends this information to stakeholders using the `AWS Email Service`. This entire pipelined output is plotted in real time which uses data from the kafka stream.
Detailed end to end implementation along with setups of each of the AWS services used is attached in this [playlist](https://www.youtube.com/playlist?list=PL4hC71cd7Y0uuEMHhh7SLTFA1xEjjdvj1).

### Task 1:
**Deploying Log generating application over EBS**

We deploy multiple instances of log generating application over AWS Elastic Beanstalk (EBS). Detailed implementation & steps to execute are present in [LogFileGenerator](https://github.com/stoic-devv/LogFileGenerator).

### Task 2:
**Real-time file monitoring**

In this we monitor and extract real-time changes to the files present in a specified directory using Akka Actors. Here is the code and detailed documentation [FileWatcher](https://github.com/parth-d/FileWatcherScala-CS441-).

### Task 3:
**_Amazon Managed Streaming Kafka:_**

This amazon service will help us capture events and stream the log file and send it further to Spark for processing. Steps to execute the Amazon MSK is provided in [Kafka MSK](https://github.com/sharathbhargav/CS441-Project/tree/main/Kafka_MSK) .

### Task 4:
**_Spark:_**

Spark's functionality is to process logs in realtime and analyse patterns that emerge over time. This application receives continuous stream of logs. These are received from a Kafka topic. When the threshold for the log type WARN and ERROR are reached, an email is triggered using the AWS Email Service. Detailed explanation with steps are provided in [Spark](https://github.com/sharathbhargav/CS441-Project/tree/main/spark_app2). 

### Task 5:
_**_Visualization_**_

This is the frontend module of the project where data visualization would be done. The aggregated results received from Spark are written to another Kafka Topic. Then, dynamic plots are drawn using data from the kafka stream. Implementation and thorough explanation is provided in the [frontend](https://github.com/sharathbhargav/CS441-Project/tree/main/frontend) repository.

<h3 align="center"><b>Developed with :heart: by <a href="https://github.com/stoic-devv">Aditya Kanthale</a>,<a href="https://github.com/parth-d"> Parth Deshpande</a>,<a href="https://github.com/JeetMehta99"> Jeet Mehta</a>,<a href="https://github.com/sharathbhargav"> Sharath Bhargav</a> and <a href="https://github.com/harshm16">Harsh Mishra</a>.</b></h1>
