# First Use
# 第一次使用

> 本项目长期更新,建议使用最新稳定版本.

> 本文档标准适用于`HeyTranser 1.0`


---
> <b>警告:</b>使用前请确保正确安装所有核心组件,并包含所使用的默认规则文件.如未安装,请先阅读[`setup.md`](setup.md).

## Step1 使用`Reader`取出全部字符串并新建工程

当你运行`Reader.exe -h`时,显示如下输出表明程序完整并可运行.

```powershell
    __  __          ______
   / / / /__  __  _/_  __/________ _____  ________  _____
  / /_/ / _ \/ / / // / / ___/ __ `/ __ \/ ___/ _ \/ ___/
 / __  /  __/ /_/ // / / /  / /_/ / / / (__  )  __/ /
/_/ /_/\___/\__, //_/ /_/   \__,_/_/ /_/____/\___/_/
           /____/

HeyTranser Reader
Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -r RLANG, --rlang=RLANG
                        Language which used by project
  -a PLANG, --plang=PLANG
                        程序语言/自定义语言规则
  -f FIRST, --first=FIRST
                        是否首次
  -t ISTRS, --istrs=ISTRS
                        是否已部署trs函数
  -i ISID, --isid=ISID  trs函数是否带ID
  -d FUNCRRULE, --funcrrule=FUNCRRULE
                        自定义指定/排除函数规则
  -s STRINGRULE, --stringrule=STRINGRULE
                        自定义指定/排除字符串规则
  -p PROJECTDIR, --projectdir=PROJECTDIR
                        工程根目录
  -o HTPROJECT, --htproject=HTPROJECT
                        HT工程根目录
  -q QZFOMMAT, --qzfommat=QZFOMMAT
                        强制使用格式
Thanks for using!
```

翻译过来就是如下信息:


| 简写  | 完整  | 格式  | 意义 |  备注 |
| :------------: | :------------: | :------------: | :------------: | :------------: |
| -r  | --rlang=  | 字符串  |  Language which used by project |  遵循`IETF`标准 |
| -a  |  --plang= |  字符串 | 程序语言/自定义语言规则  |  不要填入目前不支持的语言 |
| -f  |  --first= | T/F(可选)  |  是否首次 |  意义是是否创建新工程,默认为T | 
| -t  |  --istrs= | T/F  | 是否已部署trs函数  |   |
|  -i | --isid=  | T/F  |  trs函数是否带ID |  -t 参数为F的话,此选项强制为F |
|  -d |  --funcrrule= |  字符串(文件夹目录)(可选) |  自定义指定/排除函数规则 |   |
| -s  | --stringrule=  | 字符串(文件夹目录)(可选)  |  自定义指定/排除字符串规则 |   |
| -p  |  --projectdir= | 字符串(文件夹目录)  |  工程根目录 |  <b>注意:暂时仅支持绝对路径</b> |
| -o  | --htproject=  |  字符串(文件夹目录)(可选) | HT工程根目录  |  若空,则默认为项目目录下`HeyTranser`文件夹 |
|  -q | --qzfommat=  |  T/F(可选) | 强制使用格式 |  默认为F,<b>若不了解,强烈建议不要选T</b> |
|  -h |  --help | 无  |  帮助 |   |
| (无)  | --version  | 空  | 输出版本  | 只返回版本,其他参数无效  |
| 1  |   |   |   |   |

这里是所有需要的参数.

下一步就是根据文档填参数信息,

这里展示的是一个标准的首次创建项目所需的参数.

```powershell
Windows:
reader.exe --rlang=en --plang=python --first=T --istrs=F --isid=F --projectdir=C:\\workspace\\

Linux/MacOS:
python reader/main.py --rlang=en --plang=python --first=T --istrs=F --isid=F --projectdir=/home/workspace/

```

> 在`Reader`运行过程中会有一些输出,如果您在使用时出现问题,可以复制这些内容并在`GitHub`或`Gitee`开一个`issue`问问大家.

---

## Step2 检查项目字符串

如果你的第一步没有问题,现在应当及时看一下你的翻译项目文件,并检查里面的字符串是否正常.

待翻译内容应该位于这个地方:
```yaml
Res:
- Item:
    CheckTime: ''
    Checker: []
    ID: 1
    IsClock: false
    Resource: 'Hello World!'
    Tag: 'UnTr'
    TransResource: 
        zh-hans:
    TransTime: ''
    Translator: []


- Item:
    CheckTime: ''
    Checker: []
    ID: 2
    IsClock: false
    Resource: 'Welcome'
    Tag: 'UnTr'
    TransResource: {}
    TransTime: ''
    Translator: []
```

> <b>注意:如果您不了解`HeyTranser`运行过程和`yaml`语法,千万不要随便在此修改任何内容</b>

如果发现有不需要翻译的内容,可以删除.像这样把ID=1的字符串删掉:

```yaml
Res:
- Item:
    CheckTime: ''
    Checker: []
    ID: 2
    IsClock: false
    Resource: 'Welcome'
    Tag: 'UnTr'
    TransResource: {}
    TransTime: ''
    Translator: []
```

不要担心,ProjectManager在每次运行时都会尝试重新排序ID并询问您是否需要更新代码.

## Step3 运行一次`Writer`吧

> <b>警告:</b>使用`Writer`前请保证源代码已备份,运行Writer可能会导致不可预计的问题.



当你运行`writer.exe -h`时,显示如下输出表明程序完整并可运行.

```powershell
    __  __          ______
   / / / /__  __  _/_  __/________ _____  ________  _____
  / /_/ / _ \/ / / // / / ___/ __ `/ __ \/ ___/ _ \/ ___/
 / __  /  __/ /_/ // / / /  / /_/ / / / (__  )  __/ /
/_/ /_/\___/\__, //_/ /_/   \__,_/_/ /_/____/\___/_/
           /____/

HeyTranser Writer

Options:
  --version             show program's version number and exit
  -h, --help            show this help message and exit
  -p DIR, --projectdir=DIR
                        工程根目录
  -t DIR, --htproject=DIR
                        HT工程
  -s T/F, --first=T/F   是否首次
  -a T/F, --issave=T/F  是否以注释方式将翻译信息保存至文件
  -f T/F, --isfullfunc=T/F
                        完整/直接trs函数
  -d T/F, --isautosdk=T/F
                        是否手动引入SDK
  -b T/F, --isfullback=T/F
                        是否完整回显
  -g LEVEL, --loglevel=LEVEL
                        日志级别

Thanks for using!

```

翻译过来就是如下信息:


| 简写  | 完整  | 格式  | 意义 |  备注 |
| :------------: | :------------: | :------------: | :------------: | :------------: |
| -t  | --htproject=  |  DIR | HT工程根目录  |  填HT项目文件的根目录 |
| -s  | --first=  |  T/F(可选) | 是否首次  |  默认为T |
| -a  | --issave=  |  T/F(可选) | 是否以注释方式将信息保存至文件  |  默认为T,详见高级操作 |
| -f  | --isfullfunc=  |  T/F(可选) | 完整/直接`trs`函数  |  默认为F,详见高级操作 |
| -d  | --isautosdk=  |  T/F(可选) | 是否手动引入`SDK`  |  默认为F,意义为是否以自己手动引入`SDK` |
| -g  | --loglevel=  |  LEVEL(可选) | 日志级别  |  默认为`Warning`,详见高级操作 |
| -p  | --projectdir=  |  DIR(可选) | 工程根目录  | <b>已废弃,不建议填入,</b><i>`Writer`会自动读取项目制定的目录.</i> |

像`Reader`一样,`Writer`也需要带一些参数:

```powershell
Windows:
writer.exe --first=T --htproject=C:\\workspace\\HTProject\\

Linux/MacOS:
python writer/main.py --first=T --htproject=/home/workspace/HTProject/

```

> 你是不是觉得`Writer`参数带的少就简单?
> 
> `Writer`是这个项目最复杂的核心组件...


运行完成后,一定要看看更改后的代码,最好每个字符串的地方都检查一遍!!!

## Step4 用Transtar开始翻译吧!

> 注意:`Transtar`仍在Demo阶段(演示版),可能会导致HT工程无法使用.几率为90% : )

> Transtar并非唯一的翻译IDE,你甚至可以直接修改工程文件来翻译.[ 好像之前说过不要随便改工程文件,我撤回 ( :  ]

## Step5 剩下的工作交给ProjectManager吧

> 注意:`ProjectManager`仍在Demo阶段(演示版),可能会导致HT工程无法使用.几率为30% : )


`ProjectManager`可以统一调控`Writer/Reader/Publisher`,及时对项目进行字符串调取/代码修改/编译翻译后文件,并自动放到指定位置.

---

## (可选) 在`.gitignore`文件里添加点东西

如果你的代码库托管在GitHub或其他Git版本管理系统中,你需要修改`.gitignore`文件让HT项目文件夹里的一些临时文件不被上传,如一些日志.
```
*.trstemp
*.trscall
```

## (可选) 使用自定义规则

> 注意:`自定义规则`仍在Demo阶段(演示版),可能会失效.建议手动删除字符串.

正则表达式听说过吗?(不知道就算了吧)
        (?P<WHITESPACES>[ \t]+)(?P<NUMBER>[0-9]+\b)(?P<NAME>n\b)(?P<PARENTHESIS>[()])(?P<OPERATOR>[-*/%+?:]|[><!]=?|==|&&|\|\|)(?P<INVALID>\w+)                           