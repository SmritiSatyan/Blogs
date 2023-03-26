# Introduction

While developing software or testing a piece of code, your first instinct when something goes wrong or results in an error would be to check the logs associated with the piece of code that resulted in the error. The next step would be to investigate those logs and try to understand what it is trying to imply.

Logs, in general, are not always easy to read and understand. Regular expressions are used to parse logs and extract information. It may not always be a good idea to build regular expressions to interpret log data. 

You can easily interpret design logs by setting a standard to implement the logs. This implementation is known as the [Unified Logging Layer](https://www.fluentd.org/blog/unified-logging-layer). 
A unified logging layer helps user data in a better manner and iterates efficiently on the developed software. You can use different formats for the implementation: JSON, protobuf, and so on. FluentD uses JSON as the unifying format in most instances. This way, FluentD can combine all aspects of processing log data. Processing includes data collection, filtration, buffering, and providing this processed data as output to multiple sources and destinations. Another reason FluentD uses JSON as the output format is that it is easier to process data with JSON since JSON has a structure that is easily accessible as well as retaining flexible schemas. 
The unifying standard is more important than the specificity of the interface. 

## Introduction to Fluentd
Fluentd is an open-source, Apache 2.0 licensed software to collect data/events from different sources and write them to sources such as RDBMS, NoSQL, Hadoop, SaaS, and so on. Fluentd decouples the data/event by implementing a unified logging layer on the data collected thereby unifying the logs generated, resulting in a uniform logging infrastructure. This unification allows developers to use the different types of logs generated.

### Advantages of FluentD

1. **Simple:** You can set it up in less than 10 minutes! 
2. **Flexible:** It provides several plugins (they are easy to write and deploy!) thereby providing compatibility to be used with different log types, data sources and big data platforms. 
3. **Open-source:** It is free of cost and can be customized per user's requirements.
4. **[Supportive community](https://www.fluentd.org/community])**
5. **Unified logging:** FluentD is designed as unified logging. 
6. **Source and destination agnostic:** With the right plugins set up, you can transfer logs from or to FluentD. FluentD converts the user’s input data into any supported log data type. 
7. **Lightweight:** It consumes about 40 MB RAM, i.e runs low on memory.

FluentD behaves like a pipeline through which data flows from data (log) generators to applications that make sense of this log data (let’s call it destination application). 
Every piece of data is converted from the original format to JSON and back to a format which is compatible with the destination application. This way, a single infrastructure is achieved. 

#### Why should you be aware of FluentD and use it?
If you inspect logs frequently, debug code, and develop software, then FluentD is for you. It is easy to read and interpret JSON or a single standard format of log data. FluentD implements a unified logging layer, thereby converting incoming data/logs into one standard format, that is JSON. FluentD supports about 600 plugins, providing compatibility with multiple data sources. This means with the right plugin installed with your service, you can transfer logs to and from your service’s storage. 

## What will you learn from this article?
In this article, you will be introduced to FluentD, open-source software that implements a unified logging layer to easily interpret data logs from different sources of data. You will understand how to implement FluentD using InfluxDB.

### What is FluentD?

FluentD is an open-source software written in Ruby, that consolidates data processing steps. It performs three actions:

Collects data from sources like databases, system logs, network protocols, IoT devices, Docker, Kafka, application logs (frontend and backend) and many more.
Filters and buffers this data using the unified logging layer.
Outputs data/logs to destinations such as log management systems, big data platforms, data archiving services, data warehouse, monitoring systems, middleware, alerting systems, pubsub models, and so on. 

The goal of such a system is to understand data better and use it in ways to improve user experience. It has a ‘log everything’ architecture with the scalability to collect logs from [50000+ servers](https://docs.fluentd.org/quickstart). 

## Implementing FluentD with InfluxDB

#### Pre-requisites:
**I.Setup InfluxData account**
1. You can set up your [InfluxData account](https://www.influxdata.com/) by downloading it [locally](https://docs.influxdata.com/influxdb/v2.4/get-started/). InfluxDB supports Ubuntu, RedHat, and macOS [installations](https://docs.influxdata.com/influxdb/v2.4/install/) via brew. 

In this article, you will understand how FluentD can be used with InfluxDB on macOS. 
[Here](https://imgur.com/r1FSFiz) is an image that summarizes the goal of the article, i.e collecting log data from various sources and processing it using FluentD, and routing it to relevant destinations. 

You need to set up the Influxdata account so that you can use the log generated from this data. You can set up this data/log with FluentD further, which is the goal of the article.

2. Download the InfluxDB package for [macOS](https://docs.influxdata.com/influxdb/v2.4/install/). 

**II.Configure and setup FluentD with InfluxDB**

1. Install fluentd
You can install a stable version of [FluentD](https://www.fluentd.org/download), known as td-agent. The td-agent is built on Ruby 2.7. For macOS, td-agent can be downloaded as a .dmg installer. You can download and install the dmg package for [td-agent v4](https://td-agent-package-browser.herokuapp.com/4/macosx) or [td-agent v3](https://td-agent-package-browser.herokuapp.com/3/macosx). It is recommended to use td-agent v4.

If you are using InfluxDB 2.x, you can install the [FluentD plugin](https://github.com/influxdata/influxdb-plugin-fluent) that is bundled as a gem and hosted on [Rubygems](https://rubygems.org/gems/fluent-plugin-influxdb-v2).
```
fluent-gem install fluent-plugin-influxdb-v2 -v 1.9.0
```
If you are using InfluxDB 1.x, you can install this [fluent-plugin-influxdb plugin](https://github.com/fangli/fluent-plugin-influxdb).

2. You can launch the td-agent using the launchctl command:
```
sudo launchctl load /Library/LaunchDaemons/td-agent.plist
```

3. Check logs at location ``/var/log/td-agent/td-agent.log`` to ensure that the daemon started correctly using below command:
```
less /var/log/td-agent/td-agent.log
```

4. Add configuration details to this path `` /etc/td-agent/td-agent.conf`` as shown below.
```
<source>
@type syslog
port 42185
tag system
</source>
<match system.*.*>
@type influxdb
dbname test_logs
flush_interval 8s # for testing
host YOUR_INFLUXDB_HOST # default: localhost
port YOUR_INFLUXDB_PORT # default: 8086
</match>
```

5. Restart td-agent using the below command:
```
sudo service td-agent restart
```

**III. Install chronograf**
[Chronograf](https://docs.influxdata.com/chronograf/v1.9/) is the successor to InfluxDB’s web console. You can [install](https://docs.influxdata.com/chronograf/v1.9/introduction/installation/) it on macOS, Ubuntu, Debian, RedHat, and CentOS. You can connect it to an InfluxDB instance by navigating to http://localhost:8888/. 
You will see a page like [this](https://imgur.com/6Vb6vlM) when you navigate to http://localhost:8888/.
Click on ‘Get started`, and you will see a page like [this](https://imgur.com/mE81reZ).
Click on ‘Add Connection’.
Create a database, and provide a name for it, say ‘test_logs’. This is the location where the log data will be stored.

**IV. Setup syslogs with FluentD**

Syslog is a protocol that virtually runs on every server. It collects log data of different formats but it is difficult to parse all syslog messages using a single parser due to the variety of log formats. 
1. Set up rsyslogd
Open the  /etc/rsyslogd.conf configuration file, and append ``*.* @127.0.0.1:42185`` to the end of the file. ``127.0.0.1`` is the address of your server, which you can replace with your server address. ``42185`` is the port number, and you can replace this with any port number, and ensure that the port is open for communication. 
2. Restart the rsyslogd service using the below command:
```
$ sudo systemctl restart syslog
```

This indicates rsyslogd to forward logs to port 42185 which will be ingested by FluentD.

The configuration file for td-agent (the FluentD instance for macOS) specifies that the ``flush_interval``is 8s, that is the frequency of time after which data flows into InfluxDB. 

3. Ensure InfluxDB daemon is running by running ``influxd`` in the terminal. Navigate to ``localhost:8086`` to configure InfluxDB.
It would look similar to [this](https://imgur.com/N1qP5KF). Enter the ``Username``, ``Organization Name``, and ``Bucket Name``.

4. Click on ``Continue``, and you will see a page like [this](https://imgur.com/TaQ3Fi2).

5. Click on ``Quickstart`` to see a page like [this](https://imgur.com/LGJ1v53).
6. Click on ‘Explore’ (fourth button on the left) which will show the [query interface](https://imgur.com/GlpLWjz). This interface allows you to write SQL queries to manipulate the log data that arrives at your database in InfluxDB.
7. Click on ``Submit`` after selecting the required bucket.
8. [Here](https://imgur.com/jYgzUq1) is an image that shows the data visualization.
# Conclusion
In this article, you were introduced to open-source software, FluentD which uses a unified logging layer to facilitate a pipeline so that you can make sense of log data. You were introduced to [InfluxDB](https://www.influxdata.com/), a database that works efficiently with time-series data and [InfluxData](https://github.com/influxdata). InfluxData is the creator of InfluxDB, an open-source database that helps build and manage time-series applications. You also saw how FluentD can be implemented using InfluxDB. 
