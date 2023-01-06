# docs

## 项目说明

本项目为学习交流爬虫技术所建立，主要是为大家提供一个具有一点实际意义，又不是非常困难的爬虫项目。

目前我们已经在以下网站进行了测试，所有数据已存储于数据库，各位可以自行编写程序练习，并与数据库中结果进行对照。

- 三秋书屋
- sobooks
- 书舟网
- Fast8
- Huibooks

仅供学习交流使用，请勿用于其他途径！

## 格式规范

要做好爬虫，首先就要统一格式。我们这里使用 Mongodb 作为数据存储，作为数据库，其支持 Json 格式直接写入，非常方便。当然对于本项目的数据量而言，直接使用 JSON 存储也是可以的。

一条示例数据如下所示

```json
{
  "source": "sanqiu",
  "source_id": "6847",
  "cover": "https://www.sanqiu.mobi/wp-content/uploads/2022/12/41TGF1uk3DL-200x300.jpg",
  "info": "阿兰·德波顿作品全集（套装共14册）【阿兰·德波顿】epub+mobi+azw3",
  "tags": [
    "合集套装"
  ],
  "url": "https://www.sanqiu.mobi/6847.html",
  "download_link": [
    [
      "n7m9",
      "https://www.aliyundrive.com/s/MzBnJWBmTyr"
    ],
    [
      "rzq0",
      "https://cloud.189.cn/t/imMriamQNRJz "
    ],
    [
      "sqsw",
      " https://url71.ctfile.com/f/19926471-750021006-361b59?p=sqsw "
    ]
  ]
}
```

`source` 和 `source_id` 唯一定义了一条数据，`cover`为封面图，`info`为书籍信息，由于不同网站的数据情况不一致，我们这里直接使用`info`而非常见的作者、书名、出版社、格式等字段。`url`指出目标链接，`download_link`为列表，保存了下载链接信息。