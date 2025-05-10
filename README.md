# Splunk Universal Forwarder + Nginx (Docker Compose)
This project sets up a Splunk Universal Forwarder (UF) in Docker to collect and forward Nginx logs to a local Splunk Enterprise instance.

## Services

- **splunk** – Splunk Enterprise (`localhost:8000`)
- **nginx** – Generates logs (`./nginx_logs/access.log`)
- **splunk-uf** – Forwards logs to Splunk (`splunk:9997`)

## Config

- `inputs.conf`: monitors `access.log`
- `outputs.conf`: forwards to Splunk

## Run

```bash
docker-compose up -d

Generate traffic:

curl http://localhost:8080

Then search in Splunk:


index="main" sourcetype="nginx"
