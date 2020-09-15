Getting Started with Redis Queue
===========================

Install Redis Server

Redis is an in-memory data structure store, used as a database server, cache, and message broker.
Redis is written in C programming language.
It also provides a PHP module for communication between PHP script with the Redis server.

Step 1) Make sure the Redis Server in running:
How to install Redis Server on Ubuntu 18.04: https://tecadmin.net/install-redis-ubuntu/
```
redis-server
```

Step 2) Install rq work:
```
pip install rq
```
Step 3) Export S3 key S3_BUCKET_NAME, S3_ACCESS_KEY_ID, S3_SECRET_ACCESS_KEY

Step 4) Start redis worker:
```
rq worker -s
```



