# Filebeat

Filebeat is used to collect logs from Docker containers and send them to Logstash.

## Purpose
- Collect container logs
- Add container metadata
- Forward logs to Logstash

## Workflow
Docker Containers → Filebeat → Logstash

## Configuration File
- filebeat/filebeat.yml
