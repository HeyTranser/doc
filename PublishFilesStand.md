# Publish Files Standard 
# 发布文件的标准

> 本项目长期更新,建议使用最新稳定版本.

> 本文档标准适用于`HeyTranser 1.0`

## JSON

> 因为绝大部分高级程序语言均有`json`支持库,所以在转换为发布文件的格式暂定为首选`json`.


保留如下:
```json
    "Resource": [
        {
            "Item": {
                "ID": 1,
                "Resource": "",
                "TransResource": {},
                "Tag": "",
                "Translator": [],
                "TransTime": "",
                "IsClock": false,
                "Checker": [],
                "CheckTime": ""
            }
        },
```

并附加如下部分:
```json
    "Contributor": [],
    "Author": [],
    "Member": [],
    "ProjectName": ""
```

基本上就这些.

所以整体的格式大概如此:
```json
{
    "Resource": [
        {
            "Item": {
                "ID": 1,
                "Resource": "",
                "TransResource": {},
                "Tag": "",
                "Translator": [],
                "TransTime": "",
                "IsClock": false,
                "Checker": [],
                "CheckTime": ""
            }
        },
        {
            "Item": {
                "ID": 2,
                "Resource": "",
                "TransResource": {},
                "Tag": "",
                "Translator": [],
                "TransTime": "",
                "IsClock": false,
                "Checker": [],
                "CheckTime": ""
            }
        },
        {
            "Item": {
                "ID": 3,
                "Resource": "",
                "TransResource": {},
                "Tag": "",
                "Translator": [],
                "TransTime": "",
                "IsClock": false,
                "Checker": [],
                "CheckTime": ""
            }
        }
    ],
    "Contributor": [],
    "Author": [],
    "Member": [],
    "ProjectName": ""
}
```


## XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<Resource>
		<Item>
			<ID>1</ID>
			<Resource></Resource>
			<TransResource></TransResource>
			<Tag></Tag>
			<TransTime></TransTime>
			<IsClock>false</IsClock>
			<CheckTime></CheckTime>
		</Item>
	</Resource>
	<Resource>
		<Item>
			<ID>2</ID>
			<Resource></Resource>
			<TransResource></TransResource>
			<Tag></Tag>
			<TransTime></TransTime>
			<IsClock>false</IsClock>
			<CheckTime></CheckTime>
		</Item>
	</Resource>
	<Resource>
		<Item>
			<ID>3</ID>
			<Resource></Resource>
			<TransResource></TransResource>
			<Tag></Tag>
			<TransTime></TransTime>
			<IsClock>false</IsClock>
			<CheckTime></CheckTime>
		</Item>
	</Resource>
	<ProjectName></ProjectName>
</xml>
```

