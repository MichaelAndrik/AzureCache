# Redis

Redis is an open source (BSD licensed), in-memory data structure store, used as a database, cache, and message broker. Redis provides data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps, hyperloglogs, geospatial indexes, and streams. Redis has built-in replication, Lua scripting, LRU eviction, transactions, and different levels of on-disk persistence, and provides high availability via Redis Sentinel and automatic partitioning with Redis Cluster. More information about [Redis](https://redis.io/).

## Download

Stable releases liberally follow the usual major.minor.patch semantic versioning schema.

### Docker Hub

It is possible to get Docker images of Redis from the Docker Hub. Multiple versions are available, usually updated in a short time after a new release is available. [Docker](https://hub.docker.com/_/redis/)

### In the Cloud

Get a free-for-life Redis instance with Redis Cloud Essentials. [Cloud](https://redis.com/try-free/?_ga=2.83045649.606795882.1639066481-283578108.1639066481)

### Installation

Download, extract and compile Redis with:

```console
wget https://download.redis.io/releases/redis-6.2.6.tar.gz
tar xzf redis-6.2.6.tar.gz
cd redis-6.2.6
make
```

The binaries that are now compiled are available in the src directory. Run Redis with:

```console
src/redis-server
```

You can interact with Redis using the built-in client:

```console
src/redis-cli
redis> set foo bar
OK
redis> get foo
"bar"
```

## Azure Cache for Redis

Azure Cache for Redis provides an in-memory data store based on the [Redis](https://redis.io/). Redis improves the performance and scalability of an application that uses backend data stores heavily.

Azure Cache for Redis offers both the Redis open-source (OSS Redis) and a commercial product from Redis Labs (Redis Enterprise) as a managed service. This service is operated by Microsoft, hosted on Azure, and usable by any application within or outside of Azure.

Azure Cache for Redis can be used as a distributed data or content cache, a session store, a message broker, and more. It can be deployed as a standalone. Or, it can be deployed along with other Azure database services, such as Azure SQL or Cosmos DB.

### Princing options

There exists different pricing options:

- **_Basic_**
- **_Standard_**
- **_Premium_**

Every plan is adjusted to level in which you can balance the price as you requiere. Cache size, Network performance and Number of Client Connections are the factors that contribute in a price.


More about Azure Cache for Redis pricing and features, see [Azure Cache for Redis Pricing and Features](https://azure.microsoft.com/en-us/pricing/details/cache/).

To see a complete guide on how to install and use Azure Cache for Redis, see links provided in [Google Sheet]() provided.

[`CHECK redis_azure.py`](redis_azure.ipynb) for an example of how to use the redis-py package.

## API Management

To use API Management, administrators create APIs. Each API consists of one or more operations, and each API can be added to one or more products. To use an API, developers subscribe to a product that contains that API, and then they can call the API's operation, subject to any usage policies that may be in effect.

### Add caching to improve performance in Azure API Management

API Management policies are configurable modules that you can add to APIs to change their behaviors. Policies can do things like cache responses, transform documents and values, call webhooks for notification or audit purposes, and retry requests after transient failures. This module will use policies to enable caching in order to improve API performance under load.

APIs and operations in API Management can be configured with response caching. Response caching can significantly reduce latency for API callers and backend load for API providers.

For more detailed information about caching, see [API Management caching policies](https://docs.microsoft.com/en-us/azure/api-management/api-management-caching-policies) and [Custom caching in Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-sample-cache-by-key).

[Click here](https://docs.microsoft.com/en-us/learn/modules/improve-api-performance-with-apim-caching-policy/) to a complete guide on how to add caching to Azure API Management.

## Use an external cache

API Management instances usually have an `internal cache`, which is used to store prepared responses to requests. However, if you prefer, you can use an external cache instead. One possible external cache system that you can use is the `Azure Cache for Redis` service.

You might choose to use an external cache because:

- You want to `avoid the cache being cleared` when the API Management service is updated.
- You want to `have greater control` over the cache configuration than the internal cache allows.
- You want to `cache more data` than can be stored in the internal cache.

Another reason to configure an external cache is that you want to use caching with the `consumption pricing tier`. This tier follows serverless design principal and you should use it with serverless web APIs. For this reason, `it has no internal cache`. If you want to use caching with an API Management instance in the consumption tier, you must use an external cache.

To see a **SUMMARY FROM ALL METHODS** follow this [link](https://docs.google.com/spreadsheets/d/1P30AN88s0LwahxEQr-1ZnEdPYr2wVWs6mpnstRrp5oE/edit?usp=sharing).
