# New Relic Kafka Integrations on HOST

New Relic Kafka Connector

Folder: 
```connect-integration-jmx```

Bulding:
```docker build . -t nr-builder-bins```

Run:
```docker run -d --name nr-builder nr-builder-bins```

Copy Binares from /binares:

``docker cp nr-builder:/binares/nri-jmx /var/db/newrelic-infra/newrelic-integrations/bin/``

``docker cp nr-builder:/binares/nrjmx /usr/bin/``

``docker cp nr-builder:/binares/nrjmx.jar /usr/bin/``
