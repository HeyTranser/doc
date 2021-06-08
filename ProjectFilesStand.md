# Project Files Stand
# 项目文件标准

> 本项目长期更新,建议使用最新稳定版本.

> 本文档标准适用于`HeyTranser 1.0`

我本人认为,`yaml`是一个非常易读易改的格式,甚至用普通编辑器也可以优美的修改.所以选择`yaml`作为项目文件格式.

基本的格式就是如此:
```yaml
IsNew: true
ProjectConfig:
  Author: []
  BuildTime: ''
  Contributor: []
  HTVersion: '1.0'
  HTsite: ''
  IsClock: false
  IsFinish: false
  LastChange: ''
  License: ''
  Member: []
  NeedCheck: true
  PVersion: ''
  ProjectLocal: ..
  ProjectName: ''
  ResoureLanguage: ''
  Website: ''
  describtion: ''
Res:
- Item:
    CheckTime: ''
    Checker: []
    ID: 1
    IsClock: false
    Resource: ''
    Tag: ''
    TransResource: {}
    TransTime: ''
    Translator: []
- Item:
    CheckTime: ''
    Checker: []
    ID: 2
    IsClock: false
    Resource: ''
    Tag: ''
    TransResource: {}
    TransTime: ''
    Translator: []
- Item:
    CheckTime: ''
    Checker: []
    ID: 3
    IsClock: false
    Resource: ''
    Tag: ''
    TransResource: {}
    TransTime: ''
    Translator: []
    #以此类推
Rule:
  Custom:
    func: []
    string: []
  CustomFile: ''
  ReaderRule: []
  ReaderRuleFile: ''
  WriterRule: []
  WriterRuleFile: ''
```

## FAQ

#### 问:为什么要把所有语言的翻译整合到一个项目文件?

 答: 我认为项目文件应该尽量整合,方便项目管理.而发布文件必须只输出单语言.