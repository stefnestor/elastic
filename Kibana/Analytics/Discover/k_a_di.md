[Elastic Doc](https://www.elastic.co/guide/en/kibana/current/discover.html)

## page_load

### 1.indexPattern

```
POST /api/saved_objects/_bulk_get [{"id":"${INDEX_PATTERN_ID}","type":"index-pattern"}]
```

### 2.indexPatternFields

```
GET /api/index_patterns/_fields_for_wildcard
```

### 3.searchData

```
/internal/bsearch
```

or

```
/internal/_msearch
```

if `courier:batchSearches:false` from Kibana's Advanced Settings

## screenshots_by_version

TBD

## timeline

- (7.11.1 <= version <= 7.14.0) [Kibana not compressing some HTTP responses kibana#94998](https://github.com/elastic/kibana/issues/94998)
