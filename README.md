# Start Elasticsearch & Kibana

Before stating, check the docker memory allocation and :

```sh
    docker-compose up
```

## Create an Index

- `PUT` request : http://localhost:9200/INDEX_NAME/

## List all Indexes

- `GET` request :  http://localhost:9200/_cat/indices?v

## Add a Document

- `POST` request : http://localhost:9200/INDEX_NAME/_doc

```sh
    { 
        "name": "xyz" 
    }
```

## Query Documents in index

- `GET` request : http://localhost:9200/INDEX_NAME/_search?q=xyz

- `GET` request : http://localhost:9200/INDEX_NAME/_search?q=name:xyz

## Query Documents

- `GET` request : http://localhost:9200/_search

```sh
    {
        "query" : {
            "term" : { "name" : "xyz" }
        }
    }
```

## Get first 1000 Documents in index

-  `GET` request : http://localhost:9200/INDEX_NAME/_search?size=1000

## Remove Documents in Bulk

- `POST` request : http://localhost:9200/INDEX_NAME/_delete_by_query

```sh
    {
        "query": { 
            "match": {
                "name": "xyz"
            }
        }
    }
```

# Licence

The MIT License

Copyright (c) 2019 JUST1B

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.