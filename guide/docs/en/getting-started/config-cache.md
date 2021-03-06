# Distributed cache configuration

The SS CMS system supports two types of caching: native caching and Redis distributed caching. With Redis, caching can achieve distributed deployment. It is recommended to use in formal environments.

If Redis cache, Redis connection information is stored in the environment variable or `sscms.json` configuration file, if it is a formal environment, Redis will usually re-connection information is stored after being encrypted, if it is a local test environment, it can not encrypt stored in clear text.

::: warning NOTE
If the SS CMS is deployed in API separation mode, Redis cache must be used so that data can be synchronized between the background server and the API server.
:::

## Configure distributed cache in the installation wizard

Select the Redis cache type in the interface of the SS CMS installation:

![Select the Redis cache type](/docs/guide/images/getting-started/config-cache/redis.png)

* If the Redis port uses a non-default port, select and set a custom port.

Click Next to enter the administrator settings interface. If it is a formal environment, check the bottom to encrypt the Redis connection string:

![encrypt the Redis connection string](/docs/guide/images/getting-started/config-cache/security.png)

## Configure Redis in sscms.json

After the system is installed, SS CMS system will Redis connection information stored in `sscms.json` the configuration file:

* IsProtectData: Whether the Redis connection is encrypted storage
* SecurityKey: encryption key, randomly generated by the system
* Redis:ConnectionString: Redis connection string

If unchecked, Redis connection information will be stored in clear text:

```json
{
  "IsProtectData": false,
  "SecurityKey": "31410d60633f180c",
  "Redis": {
    "ConnectionString": "localhost:6379,allowAdmin=true"
  }
}
```

If checked, the system will encrypt Redis connection information, and the encryption key is randomly generated by the system SecurityKey:`SecurityKey`: 

```json
{
  "IsProtectData": true,
  "SecurityKey": "c5524b78e134490a",
  "Redis": {
    "ConnectionString": "QscCOGmjN84oxw1Kvsa8Z4G7rg6zbz0Z2Hfs8tPaLvI0equals00secret0"
  }
}
```

If the Redis connection changes, you need to modify the configuration file so that the SS CMS can connect to Redis correctly.

## Configure Redis in environment variables

It is recommended to use environment variables to store Redis connection information:

```bash
set SSCMS_ISPROTECTDATA="False"
set SSCMS_SECURITYKEY="31410d60633f180c"
set SSCMS_REDIS__CONNECTIONSTRING="localhost:6379,allowAdmin=true"
```

After setting the connection information Redis environment variable may be sscms.jsonthe value corresponding to the priority information acquired from the connection Redis environment variable is empty, the system.