# New Relic - Kafka Integrations on HOST

## New Relic Kafka Connector

Folder: 
```connect-integration-jmx```

1) Building and Run container:

Bulding:
```docker build . -t nr-builder-bins```

Run:
```docker run -d --name nr-builder nr-builder-bins```


2) Copy Binares from /binares:


nri-jmx:

``docker cp nr-builder:/binares/nri-jmx /var/db/newrelic-infra/newrelic-integrations/bin/``

nrjmx:

``docker cp nr-builder:/binares/nrjmx /usr/bin/``

nrjmx.jar:

``docker cp nr-builder:/binares/nrjmx.jar /usr/bin/``

3) Install openjdk8-jre

apt: ```apt install openjdk-11-jre-headless```
apk: ```apk add openjdk8-jre```
yum: ```yum install java-1.8.0-openjdk```

4) Copy the YAMLS from YAMLS folder

5) Restar Agent
