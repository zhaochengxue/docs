# IConfigApi.RemoveConfig method

删除当前插件的配置信息。

```csharp
public bool RemoveConfig(string pluginId, int siteId, string key = "")
```

| parameter | description |
| --- | --- |
| siteId | 站点Id。 如果插件的配置信息与站点无关，可以将siteId设置为 0。 |
| key | 需要删除的配置信息键。 |

## Return Value

如果删除成功，则为true；否则为false。

## See Also

* interface [IConfigApi](../IConfigApi.md)
* namespace [SiteServer.Plugin](../../SiteServer.Plugin.md)

<!-- DO NOT EDIT: generated by xmldocmd for SiteServer.Plugin.dll -->
