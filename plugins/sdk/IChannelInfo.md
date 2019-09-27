# IChannelInfo interface

栏目实体接口。 对应数据库中的siteserver_Channel表。

```csharp
public interface IChannelInfo
```

## Members

| name | description |
| --- | --- |
| [AddDate](IChannelInfo/AddDate.md) { get; set; } | 栏目添加时间。 |
| [Attributes](IChannelInfo/Attributes.md) { get; } | 栏目可扩展属性，以键/值对的方式存储栏目数据，键不区分大小写。 除了存储栏目本身数据，还将用于存储栏目的自定义字段数据。 |
| [ChannelFilePathRule](IChannelInfo/ChannelFilePathRule.md) { get; set; } | 下级栏目的页面命名规则。 |
| [ChannelName](IChannelInfo/ChannelName.md) { get; set; } | 栏目名称。 |
| [ChannelTemplateId](IChannelInfo/ChannelTemplateId.md) { get; set; } | 栏目模板Id。 |
| [ChildrenCount](IChannelInfo/ChildrenCount.md) { get; set; } | 下级栏目数量。 |
| [Content](IChannelInfo/Content.md) { get; set; } | 栏目正文，以编辑器提交信息。 |
| [ContentFilePathRule](IChannelInfo/ContentFilePathRule.md) { get; set; } | 栏目下内容的页面命名规则。 |
| [ContentModelPluginId](IChannelInfo/ContentModelPluginId.md) { get; set; } | 内容模型插件设置，只能设置一个内容模型插件，设置后此栏目下的内容表将由插件定义。 |
| [ContentRelatedPluginIds](IChannelInfo/ContentRelatedPluginIds.md) { get; set; } | 内容关联插件设置，可以设置多个关联插件。 多个关联插件以英文逗号隔开。 |
| [ContentTemplateId](IChannelInfo/ContentTemplateId.md) { get; set; } | 内容模板Id。 |
| [Description](IChannelInfo/Description.md) { get; set; } | 页面描述。 |
| [FilePath](IChannelInfo/FilePath.md) { get; set; } | 栏目生成页面路径。 |
| [GroupNameCollection](IChannelInfo/GroupNameCollection.md) { get; set; } | 栏目组。 多个栏目组以英文逗号隔开。 |
| [Id](IChannelInfo/Id.md) { get; set; } | 栏目Id。 |
| [ImageUrl](IChannelInfo/ImageUrl.md) { get; set; } | 栏目图片，存储图片地址。 |
| [IndexName](IChannelInfo/IndexName.md) { get; set; } | 栏目索引。 |
| [IsLastNode](IChannelInfo/IsLastNode.md) { get; set; } | 是否最后一级栏目。 |
| [Keywords](IChannelInfo/Keywords.md) { get; set; } | 关键字列表，各关键词间用英文逗号分割。 |
| [LinkType](IChannelInfo/LinkType.md) { get; set; } | 链接类型，设置此栏目的链接与子栏目及内容的关系。 |
| [LinkUrl](IChannelInfo/LinkUrl.md) { get; set; } | 外部链接，设置后链接将指向此地址。 |
| [ParentId](IChannelInfo/ParentId.md) { get; set; } | 父栏目Id。 |
| [ParentsCount](IChannelInfo/ParentsCount.md) { get; set; } | 上级栏目数量。 |
| [ParentsPath](IChannelInfo/ParentsPath.md) { get; set; } | 上级栏目路径，包含所有上级栏目的Id，以英文逗号分隔。 |
| [SiteId](IChannelInfo/SiteId.md) { get; set; } | 栏目所在的站点Id。 |
| [Taxis](IChannelInfo/Taxis.md) { get; set; } | 排序。 |

## See Also

* namespace [SiteServer.Plugin](../SiteServer.Plugin.md)

<!-- DO NOT EDIT: generated by xmldocmd for SiteServer.Plugin.dll -->