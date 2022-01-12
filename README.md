# new-job
FROM ubuntu
RUN apt-get update && apt-get upgrade -y
RUN apt-get install wget -y
RUN wget https://github.com/prometheus/prometheus/releases/download/v2.19.0/prometheus-2.19.0.linux-amd64.tar.gz
RUN tar -xzf prometheus-2.19.0.linux-amd64.tar.gz
RUN mkdir /logs
CMD ./prometheus-2.19.0.linux-amd64/prometheus --config.file=/logs/prometheus.yml 
