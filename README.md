# Container-WOW-Honeypot
TBD

## Usage

```bash
git clone ${this-repository}
cd container-wowhoney
docker-compose up -d
# wait a sec for the containers to be up
repeat 10 curl localhost:8080 # access wowhoney 10 times
docker logs fluentd | tail -10 | cut -d " " -f5- | jq .
```
