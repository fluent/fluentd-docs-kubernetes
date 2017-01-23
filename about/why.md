# Why Fluentd ?

Data collection is hard.

In a containerized environment, each deployed application likely have their own way to compose their logging messages, in other words, each application unit use their own format to write messages.

[Fluentd](http://www.fluentd.org) is a flexible and safe solution that can deal with:

- Different sources of information: logs, tcp, syslog...
- Different data formats: raw text, json, msgpack...
- Deliver logs to multiple destinations: MongoDB, Elasticsearch, InfluxDB, MySQL...

> tip: Fluentd community have built more than 500 plugins!

[Fluentd](http://www.fluentd.org) is a cloud native project widely used around the globe, originally made and currently maintained by [Treasure Data](http://www.treasuredata.com), since December of 2016 is hosted by the [Cloud Native Computing Foundation](http://cncf.io) ([CNCF](http://cncf.io))
