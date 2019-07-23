自定义PlantUml和C4 Model样式
---
![流程图](https://www.plantuml.com/plantuml/png/RLAnRjim4Dtv5TSfzc1fwIGNQ8eW3RgqWJ9qB5ZgP14vaIhl65T_7rACR1WG1u6wU-_ntIFlMNIGE19e8_RDodnmU3wm7YT2zSawGx7360W6aOcRkWxwN9si3F5lP0p6Eq4dbV5Z_JzgDsCzaNPPyS0o4nxCvthKB1XgumDMK-geEuWkCSR411aGUa_apzQTWAn3qAw3cxODd7OU8YEGDvfeLdUhERZgggVsyV7ddszj--ktKcgPJJKFPCth2uOtGgc694xOuh-8BBlzKJLfNfZq2O_Azh1xJhlAknSqCQGq7WOqh_limi5EGiIzWhIQ3zWFPnUHNCjiozzzEElGVLqvpXT6OGLla1boQi4J5-9ApbNh8i9KO2cF3PcoMFnqAQ3hR7yZPVdPirpOC_8jVVMVKDd_bwiKCPRJjk1FcD7Rvrv0RIfZABWLKsHxJPm2BALii_CGiBC1pORNPcsjUHmNcP9r8VSbxEqvcu-hW50k-wYs1soAuUKDWE0uaHQyCRzyrHBvVVg98xq3)

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
![时序图](http://www.plantuml.com/plantuml/png/PP11QnD15CVlyocUlUIKh8YdfOHkDb71QY6RKZo5SVRP3CxEh3DlMkFDIp7W9r1FuaamX-95qNuQr_JcLt2cNMaMOM4PVk_t_y-RFKVSagyKkoMrKBv4RnKiY6gN9edbfuDZIGl_r3kqmcX2JGDXgkIbvtg9IQsuZdRVqL9XNznDAku8RIACnK4TStlWTJ2gO08j49uPfSofrCUWf4RWkeGEbjOHa87G2Ce8hjIIzVvT3cvoMMy_Ut9mE9jdnRnuE9db3qBLvVfYytEz-VxnSdM-MNzfFdtzy-Djy-QiUN_HhD_z-hRw_M7Ld9rlFhzcqybudasd1qUizsXoV_9ubhL7Hf8KmgwJhp2zStjOyAeEvm9VUDG2TvC8XennGSR2eKFBQcv92bbpJR1pxsg3N77dTe0xoBguG65qkSL7NRxFEtREMAo0_X2o5CRcoDZdiLgUSCAGhKtucHEq4TD2EWWVRvynGfP5TvH2RZ4gqxY7evkC4MEZE9B_7v-p7FhNTWHZev6LGRPc6LZKhg_LPhOLPPZPJi-knk8MARGHMmlieIvzfVu2)


可以使用常用的编辑器vscode 或者sublime 或者其他IDE工具继承PlantUml

也可以使用在线的版本
[https://www.planttext.com/](https://www.planttext.com/)

想了解更多PlantUml或者使用方法，可参考官网[http://plantuml.com/zh/](http://plantuml.com/zh/)，上面详细的中英文说明

## 什么是C4 Model
[C4 Model](https://c4model.com/) 在我眼里更像是一个标准，一个方法论。让架构师、程序员、业务人员在讨论IT系统架构时候统一维度，统一标准，更方便的理解和沟通IT系统中的真实问题。**强烈推荐**！！！

C4 模型由一系列分层的软件架构图组成，这些架构图用于描述上下文（Context）、容器(Container)、组件(Component)和代码(Code)。C4 图的层次结构提供了不同的抽象级别，每种抽象级别都与不同的受众有关

![C4 Model](https://c4model.com/img/bigbankplc-Containers.png)

这篇Infoq的文章是有一个比较详细的介绍[https://infoq.cn/article/C4-architecture-model](https://infoq.cn/article/C4-architecture-model)


## 本库只是一个样式库
本库的目的是美化PlantUml和C4 Model所绘制系统架构图的样式，统一审美而产生。

详细的使用方法，可参考sample文件夹中的示例代码
[https://github.com/xuanye/plantuml-style-c4/blob/master/samples/](https://github.com/xuanye/plantuml-style-c4/blob/master/samples/)

<!--more-->

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

![时序图](https://www.plantuml.com/plantuml/img/PP71RjD054NtxoiUtMJb625MKHNLTW9852h5gQgkec7yQ4QCPypCk2Nis5H4wXS0AzGL4bbKR43Ghy6aEtw16MFKH4YMxD5vzzvvrtlMCUFgKgAbbpKfJf5bPIK9xWZ5PLrGRIJEdQli88uDE-kV23UldzMM3DVAaN9zhiluLStKWk9ACXNS8kiMaY9-FowPTMHYhWtrAq-WXxNoYj8hqSq9dsifzPbG9oY58cIgm2qiZFLV6dqYIisPb0le_RiStlf2RpyvFZYSpf9ybZyUJxD7FkfcTRt-iLf_-tYpl5glFZUNNtv_lsZUdZVlhvlLkvzVbxy-B9lpg_MdDp0PZsR9P79m1BqduuVZfzEaEu8JJXBkMl6Q1lVk3lEs7yoxldRZ08O0Z3jjyD0N0vNlL71H-J9mvq6xGIQPjJl8B2RRE2VVOx71qss-pxRK6K28m6Y8oG17-aYR5o5Qd397tbjf_zAdVi9ZDnSM_SEw6WE496ZJ0MQ6WcGIzh3krYC5ICD8zhzz1Xb6VzK1ZBGYABpOw4MuMDf2dzjvTX65dzbqJzgni4L8Q2qs5W3O8rMqVnJW3m00)


### 2. 类图

以下为示例

```
@startuml 示例类图

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

![用例图](http://www.plantuml.com/plantuml/img/9Oqx3i9030LxJW47oBgXeifLZFD48dcTbJ-2t1uYgj4KevaZsREwNcwRYTQ2ShskcICUHCxlzjfohMS5N7PBM3RPEtsAxG0DPJlhAV9GJ7Adpf5m2kv34LG1uS3qzpREqmnRVlm2)



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

![活动图](https://www.plantuml.com/plantuml/img/9Or13i8m30JlVGKy8F654wT-nQGMZUIuKRoczFTGk8r66itiu85eEatNQaLZaHXwMO7kTwB1UtvMhF48br4sWnXosHgzW-qGwifsvibngAHoeyOE6UJSkeeJ5zHNnP5CzlINkVz-izZoXGy0)


### 6. 其他组件

```
@startuml element
!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/core.puml
' uncomment the following line and comment the first to use locally
'!include core.puml


actor actor
agent agent
artifact artifact
boundary boundary
card card
cloud cloud
component component
control control
database database
entity entity
file file
folder folder
frame frame
interface  interface
node node
package package
queue queue
stack stack
rectangle rectangle
storage storage
usecase usecase
@enduml
```
![其他组件](https://www.plantuml.com/plantuml/img/7Sqx3eD034NHdbKa2m0tgLAn5MTu2aYs6VcZXDqdqDtcwCwHx5agmt3Vh4ajA9VRcjdZIUJycTvRhlMgWBVT4fPJsvM-nNQ0kh2TV8my16Dxa78ad8Ar2u8WqDFqwp73bd_y0000)



## C4 模型

### 1.System Context 

```
@startuml system-context-diagram

!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/c4_context.puml
' uncomment the following line and comment the first to use locally
'!include c4_context.puml

LAYOUT_WITH_LEGEND

title System Context diagram for Internet Banking System

Actor(customer, "Personal Banking Customer", "A customer of the bank, with personal bank accounts.")
System(banking_system, "Internet Banking System", "Allows customers to view information about their bank accounts, and make payments.")

System_Ext(mail_system, "E-mail system", "The internal Microsoft Exchange e-mail system.")
System_Ext(mainframe, "Mainframe Banking System", "Stores all of the core banking information about customers, accounts, transactions, etc.")

Rel(customer, banking_system, "Uses")
Rel_Back(customer, mail_system, "Sends e-mails to")
Rel_Neighbor(banking_system, mail_system, "Sends e-mails", "SMTP")
Rel(banking_system, mainframe, "Uses")

@enduml
```


![System Context](https://www.plantuml.com/plantuml/png/VL7DRjf04BxxAQPSe1BWIquzXQIeZHJIg11LFLd3Ck0L-sFjpXRyzXqRcq9AU_FkVl--Zuo1apNP1-sKIHjAmK39NCLFUHxmCDrfBjCwHGhAEoR7K-LjVapeQiehWwvXJoBNXYRgBhSOcKAkxeeMVkHfrQWF8JdXMU43bmHRRum_QBS3enq1kWrSFUiGvSk3-8Bn2esfis4V4TwhPyFdsSzlRwlYnzFgQ_4y_p9_-PnbhDaGB6i9PE7nX8UDnbr02riVu4ckWYE61tHxoT9Xisocs8UHIf6zfJ26mIk5w1sQC_AnUnl8umnw9FXj6tyjg34SP3ceUcPp1wYKJuxZTF0nEvcDrYV58hP7aVj7gjQf6IsUxMApq2zD1z1E-bXaxHtWsgTsHHskJSVjp1Rt11NMbheSNP1YVkIHHMt-99bFcZF4i_-g9B5Y2asXXLR1Hxzbc1zLYMv7G9S4qNudxRQoF8dEel--qN4fqrC4DAPVKya5T3FTQ7fUOtpHb0EwYAg1oObOjKs_axdugtyj_nOf2anGnGEg_GNqUfSbkKtioZR_eEEyaDwLQnz6ryB_PRUD5wlNayGjPZzQd-vUwCcQtm00)


### 2. Container 

```
@startuml container-diagram
!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/c4_container.puml
' uncomment the following line and comment the first to use locally
'!include c4_container.puml

LAYOUT_TOP_DOWN
'LAYOUT_AS_SKETCH
LAYOUT_WITH_LEGEND_CN

LAYOUT_TOP_DOWN
'LAYOUT_AS_SKETCH
LAYOUT_WITH_LEGEND

title Container diagram for Internet Banking System

Actor(customer, Customer, "A customer of the bank, with personal bank accounts")

System_Boundary(c1, "Internet Banking") {
    Container(web_app, "Web Application", "Java, Spring MVC", "Delivers the static content and the Internet banking SPA")
    Container(spa, "Single-Page App", "JavaScript, Angular", "Provides all the Internet banking functionality to cutomers via their web browser")
    Container(mobile_app, "Mobile App", "C#, Xamarin", "Provides a limited subset of the Internet banking functionality to customers via their mobile device")
    ContainerDb(database, "Database", "SQL Database", "Stores user registraion information, hased auth credentials, access logs, etc.")
    Container(backend_api, "API Application", "Java, Docker Container", "Provides Internet banking functionality via API")
}

System_Ext(email_system, "E-Mail System", "The internal Microsoft Exchange system")
System_Ext(banking_system, "Mainframe Banking System", "Stores all of the core banking information about customers, accounts, transactions, etc.")

Rel(customer, web_app, "Uses", "HTTPS")
Rel(customer, spa, "Uses", "HTTPS")
Rel(customer, mobile_app, "Uses")

Rel_Neighbor(web_app, spa, "Delivers")
Rel(spa, backend_api, "Uses", "async, JSON/HTTPS")
Rel(mobile_app, backend_api, "Uses", "async, JSON/HTTPS")
Rel_Back_Neighbor(database, backend_api, "Reads from and writes to", "sync, JDBC")

Rel_Back(customer, email_system, "Sends e-mails to")
Rel_Back(email_system, backend_api, "Sends e-mails using", "sync, SMTP")
Rel_Neighbor(backend_api, banking_system, "Uses", "sync/async, XML/HTTPS")
@enduml
```

![容器图](https://www.plantuml.com/plantuml/img/bLN1Zjf84BtxAsh9OOXa1aNAQKzX06Kc6MROcEma9wlSBg2LThVLtOP1g_tthJQsmH1jTZdPvQfNhr-zQZuuZzPNXG9Xj4UfoOvoYHkBHVIRr49LELLMmTRxqlq-7blStswatrPPvSY66jB-LfXY_5gXFj2uLAW3tiZvWwAHU3ykq7coO_4-xLhSbfmHtK2bkR9W1F1RWhLHokobte3Y942TG--pj8wV371dK4QWKeVefYK9r_ZHu-JxyzTLkdfUfhFdbwVefWbCaZJvF5zDxxl8oyFgFdsSVvm_pQB8Iwy8fYqOD7emFmiFV62hoSCTwX-1QdBWqnLHD17UsA6ed3S5sHYctTDW0cqOpBe-IiR5CUnPHoZ9EgDHrJ508KoblHkyZQ8ZSdh7WHpjOIZUCTPb_y5R-2i2_dLqXtlAKYnBJdwX32PbgQH0BuqUSEWJxZ26fBI1--BFQOZDICaTqwYfiH-y5D1CjXv227Tzi_RSomcJx7Ts9MCF4lxCar_YXaBtjciYh2nz31EzgHJQ45vQivCvEU1H_hpBcXqIgAEI_X1cBwfQI0SxYQ54Mk3pGcRDdlrunQWmcLJKoB6eNrfEqpSnVCC2MOa-5tPV8JtbuAhCCPTcPl-5cxiYToG0EUsae4jwisoOeySC7OKnD8-1JVB78_JUsLpCBUmSMDf8voroQv2QJLdKqurXoyavOCMk4fPo7fz4vU9WAdAELsR3B-J5xPLC6OeVf7FMIGQ_BXz-RfkPuJHxgklfzWjzWYGCpAt_xgmzV_L3Ab2grDK1XfkF5lpUR5N0Nx7qieRc7Lb8OOqpQm_pLx55pGuxLZBi6MR3u8JAc7hDAqmNQticRR1WCsd1WUuKPme3PgRofp77tRh6mFFG3klpdaIElf0wkn9EY_dLaGkzxrUhPSA9_RpZ6lrxJi_OTUgnNVf4ShFDpDarS8Hhbxn1geFziRSDqHsqYE5JylmqFcz-tl9_LQPtd7qYTh9y7-KBOUvWRKrHtpfxoql8Tv89o0tmx6xQdZDWdkbnOQE4OHtGA4HhZ1EH2yVrEVJhAXTksAvzibWj6w3kCBtoAz-rmeJwSQFEjyLZ9yu7BkL_gdy0)

### 3.Component

组件图

```
@startuml component-diagram
!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/c4_component.puml
' uncomment the following line and comment the first to use locally
'!include c4_component.puml

LAYOUT_WITH_LEGEND

title Component diagram for Internet Banking System - API Application

Container(spa, "Single Page Application", "javascript and angular", "Provides all the internet banking functionality to customers via their web browser.")
Container(ma, "Mobile App", "Xamarin", "Provides a limited subset ot the internet banking functionality to customers via their mobile mobile device.")
ContainerDb(db, "Database", "Relational Database Schema", "Stores user registration information, hashed authentication credentials, access logs, etc.")
System_Ext(mbs, "Mainframe Banking System", "Stores all of the core banking information about customers, accounts, transactions, etc.")

Container_Boundary(api, "API Application") {
    Component(sign, "Sign In Controller", "MVC Rest Controlle", "Allows users to sign in to the internet banking system")
    Component(accounts, "Accounts Summary Controller", "MVC Rest Controlle", "Provides customers with a summory of their bank accounts")
    Component(security, "Security Component", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")
    Component(mbsfacade, "Mainframe Banking System Facade", "Spring Bean", "A facade onto the mainframe banking system.")

    Rel(sign, security, "Uses")
    Rel(accounts, mbsfacade, "Uses")
    Rel(security, db, "Read & write to", "JDBC")
    Rel(mbsfacade, mbs, "Uses", "XML/HTTPS")
}

Rel(spa, sign, "Uses", "JSON/HTTPS")
Rel(spa, accounts, "Uses", "JSON/HTTPS")

Rel(ma, sign, "Uses", "JSON/HTTPS")
Rel(ma, accounts, "Uses", "JSON/HTTPS")

@enduml
```

![组件图](https://www.plantuml.com/plantuml/img/fLLDKzim4BtxLsnpA646oAMddXe2BL1e6HpwSSgivOsZLXyUIIRDTFhVkv8Jsm6cmqnpYRnQxRvzxyb-vmEwq6W5mkhQ6ZBXk9HOETJPAsc4Qafgd89L2BL_EvauN9zKCgoQel7aX3M1JvpmsScl1is69hL24-iT-x1HT2pUJ3JwG6uYtYow5YSrPsG7q1WEQGv0M14ihL9sBKq5IXe2D2NiRKldUMM1EuEo0fNQP0SxaF2qVdPmFVt--Nw--7evlrXSdtyu_tJMnQRv8lzuFfzTP5cGGH7CTeTXEp_ZSN390pf30KxH_8pGyWrFe-4OfhUNCArh9GK6QKsMpPWCPE1kx6iyWb7EwLpt5YiQ9evuwmS-e1TErY5DYQPg5BguS-liWop90q-NffOx0CKMm999YtLGoR29T8Z61wl9UNYG6Cz81sige71spHgTZ0u7q7H4TcCBgHAesF8RQdJIx7Td2RGCL89l2i_TRVWFDBhjj_qhwK4AseDrLepBWlkVOS02FKKiTwImhGoxCEHYHHhZRXwiOvpHXE2eaZwubCq8MJQTraUmGh_Y6R1X72Pi1G3Xg8oFgFmHe13aFVkfuWSA8k9gDLwS_mfZNVX86ADSiYNeaGq6IA9UTfb84Xpe21hW0Ini4tg6KdFRcC0hXcyy9Yfx73r1YrFEAz5jnbXBRlh8VAD3-9q1_peJZxsiJ39XPTZ442ivlb-KN7RpPGPtnBUf2yVeD5w_bbCVfOmb67zSFgkzRpauVDIv7seqtIuXRpIRRFCY69q9Uokj-Ot3dlHSnNALbcSsLaJIaVW4Y2VHEBPbf66xx7UJTBMBSvmIxhj_tzGk6f5Tb1WnLIlg4OWLjWyrUh-shknrsuV15bgYm9B-OIHudpAU0JM5zZ0mHQqEkgknBqHoJ6pDDsSh_u21UqyxXk9-Bz8GtgEa_dYwdNU49Ro6DOU8sOZehivEPuC3WrhjnKa5uplcvdfoCP_Vvfpy9yjIyVYItBfqbtQLV_xKvNL90qCzcvWozGkgwPSKUqUcvA_7Nm00)


### 4 Code 
类图上面已经演示过了

### 5. 扩展图

```
@startuml system-context-extend-diagram
!includeurl https://raw.githubusercontent.com/xuanye/plantuml-style-c4/master/c4_context.puml
' uncomment the following line and comment the first to use locally
'!include c4_context.puml

'LAYOUT_TOP_DOWN
'LAYOUT_AS_SKETCH
LAYOUT_WITH_LEGEND

title System Landscape diagram for Big Bank plc

Actor(customer, "Personal Banking Customer", "A customer of the bank, with personal bank accounts.")

Enterprise_Boundary(c0, "Big Bank plc") {
    System(banking_system, "Internet Banking System", "Allows customers to view information about their bank accounts, and make payments.")

    System_Ext(atm, "ATM", "Allows customers to withdraw cash.")
    System_Ext(mail_system, "E-mail system", "The internal Microsoft Exchange e-mail system.")

    System_Ext(mainframe, "Mainframe Banking System", "Stores all of the core banking information about customers, accounts, transactions, etc.")

    Person_Ext(customer_service, "Customer Service Staff", "Customer service staff within the bank.")
    Person_Ext(back_office, "Back Office Staff", "Administration and support staff within the bank.")
}

Rel_Neighbor(customer, banking_system, "Uses")
Rel_R(customer, atm, "Withdraws cash using")
Rel_Back(customer, mail_system, "Sends e-mails to")

Rel_R(customer, customer_service, "Asks questions to", "Telephone")

Rel_D(banking_system, mail_system, "Sends e-mail using")
Rel_R(atm, mainframe, "Uses")
Rel_R(banking_system, mainframe, "Uses")
Rel_D(customer_service, mainframe, "Uses")
Rel_U(back_office, mainframe, "Uses")

Lay_D(atm, banking_system)

Lay_D(atm, customer)
Lay_U(mail_system, customer)

@enduml
```
![扩展图](https://www.plantuml.com/plantuml/img/TLHDR-8m4BtxLynoAPNus4DFUogKQ5ijBLK1LNkAZEE0XMDdRQU0LllVT-maaBG12IcUppTlddrl7JMko2JOatKy6pAj73-w8VwvIeQ9e5j3C_9DA2QBX1T6miwvtFuOZmqzZBR2xOfDORa9YSgDcCx6nuAg4n_daYfVUsZTIV8Xknjd59kOCRkBgpwZ7Fta1Wg5UHdcWzjnIBMK-Y3K5gHG7AXAeEKMnkAN1kmBKZCgvOdSr13XStLoCv_yNgnNyMhn6iyMxozdmsGPBtz5guV7i-NzQVKOpwEVqSkC42USvB0CnC0SKLX6SmuL9uZIm5HiOKhL7dB929amfqsV5TRfZ9i1z5wviLfH6MByF0-LhuVE2TIHeDCms0QZ1d10JY6lCxqDA6EwKCwEUhU4H3YRoOsmF9wYDQ7cr6VViM0JJEyM_XB0Nmc_loa1nEMQCVZ9Lr7SdQ6LWG6OPz-UqLbFzOVW1n0APywe4re1tUWYh4EODiP1s5T6znnoUl9BAs5VmCJHqVMfyoWcg-Th7JqD2MeC6BKxN-5JWOmAUHad6lfpfM9VSeLyYZ0ZalWicD5MfmwY8zjHjUN0cmbT0D6jKjmpnsBFzNS7MqlSERU08gpNoD005U4Td9sd73GuSuOgIvaFmnDtx0ofr520L6V6UDy-1FF8Qa71iZJ1qj4qxJKzLJ1Oxmcq2dMMMqrieyk6idsiqxHiCCKJBCBfKdkIP489Yw3BkN3XjiXpRTprBly8UUCoVk5YkzkqhiaNRQujjvZXmzyQSQLatYjTs20CV0CmjGhsM1lnROKiyJsprTgzm3o_dpjq43onUmj_2cx3QdoU5nUNFDzfnUiYioyNx7hp5kItyY8qnTQQlgDiL-2iGnjNGjVj1NT4aJazOSK0hDs_xQjRtWRZkdqZBqvoZyFZG_mV)


## 参考
C4 Model的配色和实现大部分都是直接使用
[https://github.com/RicardoNiepel/C4-PlantUML](https://github.com/RicardoNiepel/C4-PlantUML)的,只有几个配色略有调整，并抽取出颜色的文件，可单独替换c4_theme 以实现其他配色