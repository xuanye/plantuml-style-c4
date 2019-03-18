自定义PlantUml和C4 Model样式
---

## 什么是PlantUml
[PlantUml](http://plantuml.com/)是一个支持快速绘制的开源项目.其定义了一套完整的语言用于实现UML关系图的描述.并基于强大的graphviz图形渲染库进行UML图的生成.绘制的UML图还可以导出为图片,以及通用的矢量SVG格式文件.

如以下代码，可实现时序图

```
@startuml
Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response

Alice -> Bob: Another authentication Request
Alice <-- Bob: another authentication Response
@enduml
```
![时序图](http://s.plantuml.com/imgw/sequence-diagram-kgdeozxa.webp)


## 什么是C4 Model
[C4 Model](https://c4model.com/) 在我眼里更像是一个标准，一个方法论。让架构师、程序员、业务人员在讨论IT系统架构时候统一维度，统一标准，更方便的理解和沟通IT系统中的真实问题。**强烈推荐**！！！

C4 模型由一系列分层的软件架构图组成，这些架构图用于描述上下文（Context）、容器(Container)、组件(Component)和代码(Code)。C4 图的层次结构提供了不同的抽象级别，每种抽象级别都与不同的受众有关

![C4 Model](https://c4model.com/img/bigbankplc-Containers.png)


## 本库只是一个样式库
本库的目的是美化PlantUml和C4 Model所绘制系统架构图的样式，统一审美而产生。


### 1.时序图

在PlantUml代码中引用

```
@startuml sequence-sample
!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/core.puml
' 如果使用本地，则需要注释上一行，取消注释下一行
'!include core.puml

' 使用红色箭头，默认为灰色
RED_ARROW


@enduml

```

![时序图](http://www.plantuml.com/plantuml/png/9OrB2i9040Ntda8FCDCRLwvobNRoC86UpjWVDBVNa5L1GL6J1rjabyjjrIOv8qskIyJm1v7nfxxMMFAP3ckR1ZHgspfzatK73M4zwkAn2qgxKsSF63dt8N1ol1FQK4vHnx6QeFEVFm00)


### 2. 类图

以下为示例

```
@startuml 交易相关主要类图

!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/core.puml
' uncomment the following line and comment the first to use locally
'!include core.puml

GREY_ARROW

abstract class BaseClass {
    +  AbstractMethod() : void
    #  VirtualMethod(s:string) : int
}
class SubClass {
    + AbstractMethod() : void
    # VirtualMethod(s:string) : int
}

interface IInterfaceA {
}

interface "IInterfaceA`1"<T> {
    Value : T <<get>>
}
class ImplementClass {
    + Value : int <<get>>
}
BaseClass <|-- SubClass
IInterfaceA <|-- "IInterfaceA`1"
"IInterfaceA`1" "<int>" <|-- ImplementClass

@enduml

```
![类图](http://www.plantuml.com/plantuml/png/9Osn3S9G30Lxfe01yjrGKMKLurWaah_pPJyBiZr4LAShJZSdE53TBhVDnMhH2hkkmCW7KV2xlJQizQpKaDsXZYPxfq-n7qh3sCzwIXocazofSqA3alimJHBZpEblRPoVMNtvyGi0)

### 3. 状态图



```
@startuml state-sample
!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/core.puml
' uncomment the following line and comment the first to use locally
'!include core.puml

GREEN_ARROW

title HTTP Request Parsing States

[*] --> RequestLine

RequestLine : Parse HTTP
RequestLine : request line
RequestLine --> Headers : Ok
RequestLine --> Error : Failure

Headers : Parse HTTP
Headers : headers
Headers --> Host : Ok
Headers --> Error : Failure

Host : Check host
Host : header is present
Host --> Length : Not chunked
Host --> Chunked : Chunked
Host --> Error : Failure

Length : Check if required,
Length : valid & size
Length --> Error : Failure
Length --> Error : Entity Too Large
Length --> [*] : Ok

Chunked : Parse HTTP
Chunked : chunk header
Chunked --> Error : Failure
Chunked --> [*] : Ok

@enduml
```
![状态图](http://www.plantuml.com/plantuml/png/9Oqn3i8m34LtJW47IBmmCVKg9hLe9SUDx6z1RmyHqzCRdjuIO4TslTnsQvghfEjr0qOyY9pVzRLZosU6U3iCOgZjwFH9jbDeADkiI-1KAUrEdGFY5Do7Ib208ULlTSpF8hR--0K0)

### 4. 用例图

```
@startuml usecase-sample
!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/core.puml
' uncomment the following line and comment the first to use locally
'!include core.puml

' 设置方向
LAYOUT_LEFT_RIGHT
'LAYOUT_TOP_DOWN
'LAYOUT_AS_SKETCH


actor customer
actor clerk

UserCasePackage("checkout","买单") {
    customer -- (checkout)
    (checkout) .> (payment) : include
    (help) .> (checkout) : extends
    (checkout) -- clerk
}

@enduml

```

![用例图](http://www.plantuml.com/plantuml/png/9Oqx3i9030LxJW47oBgXeifLZFD48dcTbJ-2t1uYgj4KevaZsREwNcwRYTQ2ShskcICUHCxlzjfohMS5N7PBM3RPEtsAxG0DPJlhAV9GJ7Adpf5m2kv34LG1uS3qzpREqmnRVlm2)



### 5. 活动图

```
@startuml activity-new-sample
!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/core.puml
' uncomment the following line and comment the first to use locally
'!include core.puml

GREEN_ARROW


start
:ClickServlet.handleRequest();
:new page;
if (Page.onSecurityCheck) then (true)
    :Page.onInit();
    if (isForward?) then (no)
        :Process controls;
        if (continue processing?) then (no)
            stop
        endif
        if (isPost?) then (yes)
            :Page.onPost();<
        else (no)
            :Page.onGet();
        endif
        :Page.onRender();
    endif
else (false)
endif
if (do redirect?) then (yes)
    :redirect process;
else
    if (do forward?) then (yes)
        :Forward request;
    else (no)
        :Render page template;
    endif
endif

stop
@enduml
```

![活动图](http://www.plantuml.com/plantuml/png/9Oqx3i9030LxJW47oBgXeifLZFD48dcTbJ-2t1uYgj4KevaZsREwNcwRYTQ2ShskcICUHCxlzjfohMS5N7PBM3RPEtsAxG0DPJlhAV9GJ7Adpf5m2kv34LG1uS3qzpREqmnRVlm2)
