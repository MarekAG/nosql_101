# Your data, Your search

Zaczynamy od lektury [What's Wrong with SQL search](http://philip.greenspun.com/seia/search).

Książka:

* [Elasticsearch – The Definitive Guide](https://www.elastic.co/guide/en/elasticsearch/guide/master/index.html)

Podręczne linki do [ElasticSearch](https://github.com/elasticsearch):

* [You know, for Search](http://www.elasticsearch.org/)
* [Stempel (Polish) Analysis for ElasticSearch](https://github.com/elastic/elasticsearch/tree/master/plugins/) –
  this plugin includes the **polish** analyzer and **polish_stem** token filter;
  dokumentacja [Elasticsearch Plugins and Integrations](https://www.elastic.co/guide/en/elasticsearch/plugins/current/index.html)
* [JSON specification for the Elasticsearch's REST API](https://github.com/elasticsearch/elasticsearch/tree/master/rest-api-spec)
* [Guides](https://www.elastic.co/guide/index.html)
* [References](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
* [Modules](https://www.elastic.co/guide/en/elasticsearch/reference/current/modules.html)
  - [text scoring in scripts](http://www.elasticsearch.org/guide/en/elasticsearch/reference/current/modules-advanced-scripting.html) –
  df, tf, ttf

## Interpretacja URI w zapytaniach kierowanych do ElasticSearch

Podstawowe terminy to: **index** i **type** wyjaśnimy na przykładach ze strony [Your Data, Your Search](http://www.elasticsearch.org/blog/2010/02/12/yourdatayoursearch.html).

Częścią Elasticsearch jest wyszukiwarka [Apache Lucene](http://lucene.apache.org/). Składnia zapytań Lucene jest opisana w dokumencie [Query Parser Syntax](http://lucene.apache.org/core/old_versioned_docs/versions/3_5_0/queryparsersyntax.html).

Tworzenie i usuwanie indeksu o nazwie *tweets* (korzystajac z programu _curl_ i _http_).

```sh
curl -XPUT localhost:9200/tweets
curl -XDELETE localhost:9200/tweets
http ...
http ...
```

Przykładowy dokument:
```json
{
  "isbn": "0812504321",
  "name": "Call of the Wild",
  "author": {
     "first_name": "Jack",
     "last_name": "London"
   },
   "pages": 128,
   "tags": ["fiction", "children"]
}
```
