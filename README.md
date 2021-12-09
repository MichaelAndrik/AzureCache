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

### Prerequisites

- Azure subscription - [create one for free](https://azure.microsoft.com/free/).
- `Python 2 or 3`

## Create an Azure Cache for Redis instance

1. To create a cache, sign in to the Azure portal and select `Create a resource`.
![Create a resource](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/includes/media/redis-cache-create/create-resource.png)
2. On the New page, select `Databases` and then select `Azure Cache for Redis`.
![Create a resource](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/includes/media/redis-cache-create/select-cache.png)

3. On the `New Redis Cache` page, configure the settings for your new cache.
4. Select the `Networking` tab or select the `Networking` button at the bottom of the page.
5. In the `Networking` tab, select your connectivity method.

6. Select the `Next: Advanced` tab or select the `Next: Advanced` button on the bottom of the page.

7. In the `Advanced` tab for a basic or standard cache instance, select the enable toggle if you want to enable a non-TLS port. You can also select which Redis version you would like use, either 4 or 6.

![Redis version](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/includes/media/redis-cache-create/cache-redis-version.png)

8. In the `Advanced` tab for premium cache instance, configure the settings for non-TLS port, clustering, and data persistence. You can also select which Redis version you would like use, either 4 or 6.

9. Select the `Next: Tags` tab or select the Next: Tags button at the bottom of the page.

10. Optionally, in the `Tags` tab, enter the name and value if you wish to categorize the resource.

11. Select R`eview + create.` You're taken to the Review + create tab where Azure validates your configuration.

12. After the green Validation passed message appears, select `Create`.

> It takes a while for the cache to create. You can monitor progress on the Azure Cache for Redis Overview page. When Status shows as Running, the cache is ready to use.

## Retrieve host name, ports, and access keys from the Azure portal

To connect to an Azure Cache for Redis instance, cache clients need the host name, ports, and a key for the cache. Some clients might refer to these items by slightly different names. You can get the host name, ports, and keys from the [Azure portal](https://portal.azure.com/).

- To get the access keys, from your cache left navigation, select `Access keys`.

![Azure Cache for Redis keys](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/includes/media/redis-cache-access-keys/redis-cache-keys.png)

To get the host name and ports, from your cache left navigation, select `Properties`. The host name is of the form `<DNS name>.redis.cache.windows.net`.

![Azure Cache for Redis properties](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/includes/media/redis-cache-access-keys/redis-cache-hostname-ports.png)

## Install redis-py

[Redis-py](https://github.com/redis/redis-py) is a Python interface to Azure Cache for Redis. Use the Python packages tool, pip, to install the redis-py package from a command prompt.

The following example used pip3 for Python 3 to install redis-py on Windows 10 from an Administrator command prompt.

![Install the redis-py Python interface to Azure Cache for Redis](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/media/cache-python-get-started/cache-python-install-redis-py.png)

[`CHECK redis_azure.py`](redis_azure.ipynb) for an example of how to use the redis-py package.
