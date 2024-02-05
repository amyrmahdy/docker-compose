.PHONY: config
config:
	rm -rf clickhouse01 clickhouse02 clickhouse03 
	#clickhouse04
	mkdir -p clickhouse01 clickhouse02 clickhouse03 
	#clickhouse04
	HOSTNAMENUMBER=1 REPLICA1=lx51_s1_r1 REPLICA2=lx51_s3_r2 SHARD1=s1 SHARD2=s3 envsubst < config.xml > clickhouse01/config.xml
	HOSTNAMENUMBER=2 REPLICA1=lx52_s2_r1 REPLICA2=lx52_s1_r2 SHARD1=s2 SHARD2=s1 envsubst < config.xml > clickhouse02/config.xml
	HOSTNAMENUMBER=3 REPLICA1=lx53_s3_r1 REPLICA2=lx53_s2_r2 SHARD1=s3 SHARD2=s2 envsubst < config.xml > clickhouse03/config.xml
#	REPLICA=04 SHARD=02 envsubst < config.xml > clickhouse04/config.xml
	cp users.xml clickhouse01/users.xml
	cp users.xml clickhouse02/users.xml
	cp users.xml clickhouse03/users.xml
#	cp users.xml clickhouse04/users.xml

.PHONY: up
up:
	docker-compose up -d

.PHONY: start
start:
	docker-compose start

.PHONY: stop
stop:
	docker-compose stop

.PHONY: down
down:
	docker-compose down
