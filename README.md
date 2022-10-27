# Tutorial for Apache Airflow

This repository contains the code I used to teach myself Apache Airflow and is based on the Udemy course, *[The Complete Hands-On Introduction to Apache Airflow](https://www.udemy.com/course/the-complete-hands-on-course-to-master-apache-airflow/)*.

## Prerequisites

* Docker
* Python 3.7+

## Instructions

The `docker-compose.yaml` file describes the set of related services and dependencies, as well as the network configuration, needed to run Apache Airflow. To launch these services, type

```
docker-compose up -d
```

Access the Airflow dashboard from `https://localhost:8080`. The default user name and password are both `airflow`, but this can be set in the `docker-compose.yaml` file.

To tear down the containers, use the command

```
docker-compose down
```

To see which containers are running, type

```
docker-compose ps
```

To access a terminal inside one of the containers, e.g. the scheduler, get the container name from the output of the previous command and then use

```
docker exec -it <container_name> /bin/bash
```

# Apache Airflow with Custom Elasticsearch Plugin

The `docker-compose-es.yaml` file adds in an additional service for running the Elasticsearch search engine. As part of this tutorial, we write a custom plugin whose code is contained in the `plugins/hooks/elastic/elastic_hook.py` file.