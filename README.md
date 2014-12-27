Redis Caching Provider for DNN Platform
========================

This caching provider allows to use a Redis cache server or cluster within DNN, using a hybrid in-memory approach to increase cache performance (items are cached in the local memory and on Redis cache). You must use Redis 2.8.17 or higher, it's also Azure Redis cache compatible. 

Quick Start
============
1) Provision a Redis cache to be used by your DNN instance. Perhaps one of the fastest ways to do it is to provision an Azure Redis cache by following the steps described at http://msdn.microsoft.com/en-us/library/dn690516.aspx, remember to provision the DNN instance on the same datacenter location to improve performance. You can also provision your Redis cache on your premises by following instructions provided at http://redis.io/download. The caching provider has been tested with the Win64 Redis port and working well.
2) Download from the https://github.com/davidjrh/dnn.rediscachingprovider/tree/master/Release folder the latest version of the DNN Redis Caching provider
3) Using the Extensions page of your DNN instance, upload and install the Redis caching provider. Once installed, will be the default caching provider. 
4) Open your web.config file and specify the RedisCachingProvider connection string in the ConnectionStrings section. If you are using Azure Redis cache, your connection string should look like this:
  <connectionStrings>
    <add name="RedisCachingProvider" connectionString="mycache.redis.cache.windows.net,password={base64password},ssl=True"  providerName="DotNetNuke.Providers.RedisCachingProvider" />
  </connectionStrings>

