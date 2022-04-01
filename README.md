# signalk-mqtt-timescaledb-grafana

## Dependencies

docker-compose is used to start local development environment dependencies. Dependencies consist of 7 containers:

    signalk/signalk-server (signalk-server)
    eclipse-mosquitto (Mosquitto MQTT broker)
    mqtt-to-timescaledb-js (MQTT to SQL javascript)
    mqtt-to-timescaledb-py (MQTT to SQL python)
    timescale/timescaledb (Time-series data extends PostgreSQL)
    grafana/grafana (Grafana development UI)
    dpage/pgadmin4 (Postres web admin UI)

## Architecture
- signalk listen on port 3000 via HTTP, no SSL, no login user/pass
- eclipse-mosquitto listen on port 1883 via MQTT, no SSL, no login user/pass 
- mqtt-to-timescaledb python and node version to convert MQTT message to SQL Queries
- timescale listen on port 5432, no SSL
- pgadmin4 listen on port 8080, no SSL

A network 172.30.0.0/24 is created. Gateway 172.30.0.1. All connections are done using the gateway IP.

## External tools
- Cross-platform NMEA / Signal K data stream generator, https://github.com/panaaj/nmeasimulator
- Cross-platform MQTT Desktop Client, https://mqttx.app

## TODO/Questions:
- Replace timescale/timescaledb with timescale/timescaledb-ha to add GeoSpatial support?
