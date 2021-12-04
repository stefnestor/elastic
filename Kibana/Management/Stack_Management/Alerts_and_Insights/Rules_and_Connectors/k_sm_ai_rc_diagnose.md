
## top_expensive

```
GET .kibana-event-log-*/_search
{ "size": 0, 
"aggs": {"rule_id": {"terms": {"field": "rule.id", "order": {"avg_ns": "desc"}, "size": 25 },
"aggs": {"avg_ns": { "avg": { "field": "event.duration" }},
        "rule_name": {"terms": {"field": "rule.name", "order": {"_count": "desc"}, "size": 1 },
"aggs": {"rule_group": {"terms": {"field": "event.category", "order": {"_count": "desc"}, "size": 1 },
"aggs": {"rule_type": {"terms": {"field": "rule.category", "order": {"_count": "desc"}, "size": 1 },
"aggs": {"avg_ns": {"avg": {"field": "event.duration"} },
        "sum_ns": {"sum": {"field": "event.duration"} } } } } } } } } } },
"query": {"bool": {"filter": [{"range": {"@timestamp": {"gte": "now-24h", "lte": "now"} } } ] } } }
```
