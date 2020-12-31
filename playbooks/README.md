# Playbooks

## Site down

Read our [Site down documentation](./site_down.md)

## Monitoring

- [http://munin.metacpan.org/](http://munin.metacpan.org/) (very basic but good quick glance)

- [https://github.com/metacpan/metacpan-monitoring](https://github.com/metacpan/metacpan-monitoring) (which is in hourly cron and sends emails)

- [https://www.panopta.com/](https://www.panopta.com/) (they give us a free account and we run their agent on our servers)


## Elasticsearch

### Quick check of status
From one of the production ES boxes
```sh
curl localhost:9200/_cat/health

curl localhost:9200/_cat/health?v
```

#### Monitor any restorations going on
```sh
 curl localhost:9200/_cat/recovery?v
 ```

### Access from your local machine

#### Create an ssh tunnel to one of the ES nodes in the cluster
```sh
ssh -L 9202:localhost:9200 lw-mc-01.metacpan.org
```
Then
```sh
curl localhost:9202/
```

### Visual status of the cluster

Set up an SSH tunnel (see above) then:

[http://localhost:9202/_plugin/kopf/#!/cluster](http://localhost:9202/_plugin/kopf/#!/cluster)


