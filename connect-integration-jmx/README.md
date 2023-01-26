# New Relic Kafka Connector

1) Build and Run container:

- Build: ```docker build . -t nr-builder-bins```

- Run: ```docker run -d --name nr-builder nr-builder-bins```

3) Copy Binares from /binares:
- nri-jmx: ```docker cp nr-builder:/binares/nri-jmx /var/db/newrelic-infra/newrelic-integrations/bin/```

- nrjmx: ```docker cp nr-builder:/binares/nrjmx /usr/bin/```

- nrjmx.jar: ```docker cp nr-builder:/binares/nrjmx.jar /usr/bin/```

4) Install openjdk8-jre

- apt: ```apt install openjdk-11-jre-headless```

- apk: ```apk add openjdk8-jre```

- yum: ```yum install java-1.8.0-openjdk```

4) Copy the YAMLS from YAMLS folder to ```/etc/newrelic-infra/integrations.d/```

- Edit the files if needed.

5) Restart Agent
