# Container-WOW-Honeypot
WIP

## Usage

```bash
git clone ${this-repository}
cd container-wowhoney
docker-compose up -d
# wait a minute for the containers to be up
docker build -t wowhoney wowhoney/
docker run --rm -d --log-driver=fluentd --log-opt tag="docker.{{.ID}}" --name wowhoney -p 8080:8080 wowhoney
repeat 10 curl localhost:8080 # access wowhoney 10 times
# wait a minute for elasticsearch to create the index
curl localhost:9200/docker/_search?pretty
```
