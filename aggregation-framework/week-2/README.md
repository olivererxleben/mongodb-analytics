# Week 2

## mongo import

### Requirements

* Atlas Account with free tuer MongoDB or a hosted MongoDB server somewhere else or your local machine
* mongo db tooling installed

### Waltkthrough

download retail csv from https://s3.amazonaws.com/edu-static.mongodb.com/lessons/coursera/aggregation/lessons/retail.csv

It is originally from UCIs machine learning repository: https://archive.ics.uci.edu/ml/datasets/Online+Retail (xlsx).

running the command like

    mongoimport --host Cluster0-shard-0/cluster0-shard-00-00-l8kpo.mongodb.net:27017,cluster0-shard-00-01-l8kpo.mongodb.net:27017,cluster0-shard-00-02-l8kpo.mongodb.net:27017 --ssl --username admin --password admin --authenticationDatabase admin --db coursera --collection orders  --type csv --file Downloads/retail.csv --headerline --columnsHaveTypes --drop --mode=upsert --upsertFields=InvoiceNo,StockCode

Note:

--host is the parameter to connect your cluster
--drop will drop

--mode=upsert will update insert => update entries already in collection or insert if  not found
--upsertFields which fields to look at when upserting