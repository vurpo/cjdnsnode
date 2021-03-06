# Cjdnsnode - The cjdns supernode [![Build Status](https://travis-ci.org/cjdelisle/cjdnsnode.svg?branch=master)](https://travis-ci.org/cjdelisle/cjdnsnode)

A supernode is a replicating database of node/link information, it's collected by scanning the
network for peers but PLEASE DON'T ENABLE SCANNING, there is another snode scanning and you can
simply connect to it's socket and listen for all of the updates sent right to your door.

Snode allows dumping of it's internal state using TCP/JSON (replication socket) and it allows
querying to get a path between any 2 nodes given by their keys using UDB/Benc.

### Setup:

(tested working on Ubuntu 16.04.2 LTS)

* `npm install`

* Install and start postgresql, and run the initdb.sql: `$ sudo -u postgres psql < initdb.sql`

* Create the config file: `$ cp config.example.js config.js`

* Start the node: `$ nodejs server.js`

### To query a path from your local node:

```bash
echo -n 'd1:q2:gr3:src54:3fdqgz2vtqb0wx02hhvx3wjmjqktyt567fcuvj3m72vw5u6ubu70.k3:tar54:1220u65349nljc5fwy1tyvm0j24bwgcj75rx09ukvd94vhg858b0.k4:txid4:abcde' | nc -u ::1 9001
```
