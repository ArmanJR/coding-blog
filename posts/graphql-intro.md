> :Hero src=/img/graphql.png,
>       leak=126px

> :Title shadow=0 0 8px black, color=white
>
> Intro to GraphQL + Laravel

> :Author src=github

<br>

# What is GraphQL?
*GraphQL* is an open-source data query and manipulation language for APIs, and a runtime for fulfilling queries with existing data. It provides an approach to developing web APIs and has been compared and contrasted with REST and other web service architectures. It allows clients to define the structure of the data required, and the same structure of the data is returned from the server, therefore preventing excessively large amounts of data from being returned, but this has implications for how effective web caching of query results can be. The flexibility and richness of the query language also adds complexity that may not be worthwhile for simple APIs. Despite the name, GraphQL does not provide the richness of graph operations that one might find in a full-fledged graph database such as Neo4j, or even in dialects of SQL that support transitive closure. For example, a GraphQL interface that reports the parents of an individual cannot return, in a single query, the set of all their ancestors.

<br>

## Example

`POST` request:
```graphql
{
    orders {
        id
        productsList {
            product {
                name
                price
            }
            quantity
        }
        totalAmount
    }
}
```
response:
```json
{
    "data": {
        "orders": [
            {
                "id": 1,
                "productsList": [
                    {
                        "product": {
                            "name": "orange",
                            "price": 1.5
                        },
                        "quantity": 100
                    }
                ],
                "totalAmount": 150
            }
        ]
    }
}
```

In this post we are going to implement GraphQL in our Laravel project.  

---

