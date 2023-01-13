# PostgreSQL docker-compose

The example project to start PostgreSQL in Replication mode. 

_Base on tutorial from https://medium.com/swlh/postgresql-replication-with-docker-c6a904becf77_

## How to use
```shell
sh docker-init.sh
```

## How it works?
1. Clear DB data folder.
2. Start Master node.
3. Prepare Replica config from master node.
   1. Create replica user
   2. Backup Master data for initial to Slave node.
   3. Init Slave node
      1. Copy slave config file such as url to connect to master node.
      2. Override `pg_hba.conf` in master node. 
4. Restart Master node to apple config
5. Start Slave node.
6. Validate by print replication slot.