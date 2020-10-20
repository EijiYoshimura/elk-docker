# elk-docker

This is a docker-compose I used to get up an ELK stack to develop and test applications that use logstash.

## What is ELK Stack?

ELK is an acronimous for three open source projects: Elasticsearch, Logstash and Kibana.

Elasticsearch is an search and analysis mechanism.
Logstash is a server side dataprocessing pipeline that receive data from inumerous sources simunitaneously, transforms and send it to another place, like Elasticseatch.
Kibana allows users to view data using diagrams and charts on Elasticsearch.
[more info](https://www.elastic.co/pt/what-is/elk-stack)

---

## How to use it?

These instructions are deducing you are a Linux user.

1. You should have installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

2. Clone the project:

```
git clone git@github.com:EijiYoshimura/elk-docker.git
```

3. Create the following directory to persist data:

```
sudo mkdir -p elastic/data
sudo chmod -R g+rwx elastic
sudo chown -R 1000:1000 elastic
```

4. As Elasticsearh uses a mmapfs directory by default to store the indices, increase the limits running the following command ([more info](https://www.elastic.co/guide/en/elasticsearch/reference/current/vm-max-map-count.html)):

```
sudo sysctl -w vm.max_map_count=262144
```

3. Run:

```
docker-compose up
```

Only it! Easy, isn't it?

---

You can access the Kibana page on URL: `http://localhost:5601/`

The Elasticsearch endpoint: `http://localhost:9200/`

---

If you have any doubts, please open an issue.

Thanks!
