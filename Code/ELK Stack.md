The Elastic stack, created by Elastic, is an open-source collection of mainly three applications (Elasticsearch, Logstash, and Kibana) that work in harmony to offer users comprehensive search and visualization capabilities for real-time analysis and exploration of log file sources. And recently we have fleet agent's doing the way of Beats and/or Logstash
![[Pasted image 20251028202437.png]]
`Elasticsearch` is a distributed and JSON-based search engine, designed with RESTful APIs. As the core component of the Elastic stack, it handles indexing, storing, and querying. Elasticsearch empowers users to conduct sophisticated queries and perform analytics operations on the log file records processed by Logstash.

`Logstash` is responsible for collecting, transforming, and transporting log file records. Its strength lies in its ability to consolidate data from various sources and normalize them. Logstash operates in three main areas:

1. `Process input`: Logstash ingests log file records from remote locations, converting them into a format that machines can understand. It can receive records through different [input methods](https://www.elastic.co/guide/en/logstash/current/input-plugins.html), such as reading from a flat file, a [[Network Protocols|TCP]] socket, or directly from [[Linux Logs|syslog]] messages. After processing the input, Logstash proceeds to the next function.
2. `Transform and enrich log records`: Logstash offers numerous ways to [modify a log record](https://www.elastic.co/guide/en/logstash/current/filter-plugins.html)'s format and even content. Specifically, filter plugins can perform intermediary processing on an event, often based on a predefined condition. Once a log record is transformed, Logstash processes it further.
3. `Send log records to Elasticsearch`: Logstash utilizes [output plugins](https://www.elastic.co/guide/en/logstash/current/output-plugins.html) to transmit log records to Elasticsearch.

`Kibana` serves as the visualization tool for Elasticsearch documents. Users can view the data stored in Elasticsearch and execute queries through Kibana. Additionally, Kibana simplifies the comprehension of query results using tables, charts, and custom dashboards.
## The Elastic Stack As A SIEM Solution

The Elastic stack can be used as a Security Information and Event Management ([[SIEM]]) solution to collect, store, analyze, and visualize security-related data from various sources.

![[Pasted image 20251028203038.png]]

### Kibana Query Language (KQL)
is a powerful and user-friendly query language designed specifically for searching and analyzing data in Kibana.

#### Basic Structure
KQL queries are composed of `field:value` pairs, with the field representing the data's attribute and the value representing the data you're searching for. 
```shell-session
event.code:4625
```
#### Free Text Search
KQL supports free text search, allowing you to search for a specific term across multiple fields without specifying a field name. 
```shell-session
"svc-sql1"
```
This query returns records containing the string "svc-sql1" in any indexed field.
#### Logical Operators
KQL supports logical operators AND, OR, and NOT for constructing more complex queries. Parentheses can be used to group expressions and control the order of evaluation. 
```shell-session
event.code:4625 AND winlog.event_data.SubStatus:0xC0000072
```
#### Comparison Operators
KQL supports various comparison operators such as `:`, `:>`, `:>=`, `:<`, `:<=`, and `:!`.
```shell-session
event.code:4625 AND winlog.event_data.SubStatus:0xC0000072 AND @timestamp >= "2023-03-03T00:00:00.000Z" AND @timestamp <= "2023-03-06T23:59:59.999Z"
```
#### Wildcards and Regular Expressions
KQL supports wildcards and regular expressions to search for patterns in field values.
```shell-session
event.code:4625 AND user.name: admin*
```