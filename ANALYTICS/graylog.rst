*******
graylog
*******

A Java server program that uses MongoDB and ElasticSearch to collect and later on do query of accumulated
and collected logs.

Traditionally, data analytics uses these three technologies together commonly known as E.L.K:
    - ElasticSearch (for data querying using Lucene syntax)
    - Logstash (for data pushing into ElasticSearch?)
    - Kibana (for data visualization)

**graylog** only uses ElasticSearch. 
