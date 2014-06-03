FROM djktno/java
MAINTAINER Daniel Kunnath <djktno@gmail.com>

# Install Elasticsearch
RUN mkdir -p /usr/share/elasticsearch
RUN wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.2.0.tar.gz -O /tmp/elasticsearch-1.2.0.tar.gz
RUN tar xfz /tmp/elasticsearch-1.2.0.tar.gz -C /usr/share/elasticsearch --strip-components=1

# Install plugins
RUN /usr/share/elasticsearch/bin/plugin -install lmenezes/elasticsearch-kopf
RUN /usr/share/elasticsearch/plugin -url http://download.elasticsearch.org/kibana/kibana/kibana-latest.zip -install elasticsearch/kibana3

# Expose port 9200
EXPOSE 9200

# Start Elasticsearch
CMD /usr/share/elasticsearch/bin/elasticsearch