# MQTT to Influx Microservice

A Python implementation of a MQTT to Influx proxy microservice,  intended as support to Internet of Things (IoT) applications. It uses the reader-writer paradigm for consuming messages.

## How to use it
Clone the repository and build it locally using the Dockerfile:
```bash
docker build -t lcarnevale/mqtt2influx .
```

Run the image:
```bash
docker run -d --rm --name mqtt2influx \
    -v /opt/lcarnevale/mqtt2influx:/etc/mqtt2influx \
    lcarnevale/mqtt2influx
```

Publish a MQTT message using your favorite client, formatting data as following:
```json
{
    "measurement": "my-measurement",
    "tags": {
        "region": "my-region",
    },
    "fields": {
        "sensor": "data"
    }
}
```