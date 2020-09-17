## 自定义 PlantUml 和 C4 Model 样式

![流程图](http://www.plantuml.com/plantuml/png/RP91Rzim38Nl-XNSgScX3Zhiv0nOXg8jTjaAzx3ZOCXq8eIcF8bQu7y_oOIz5R0EWKI-z_I9yIbA6oGDP3uujfGwX8l86El38V5uFLVM3uUHMYwQ-oWJuRtzT7ge7ggF1-i3LcCntq7Yh1oG1UI2q7iYVtDy1dACq787xzeknBppa282UTiIJUPk9VYNQrwQfwVllxuspO-VnfWPrjIFvEpr3SCVGgakEPommTy9e-psHrCptc1iptWqheVTQzvLdj_Gfk1aUhoWlUuB1SDEGiAzWRngbV4tTdD8gHMtYyy-tDhGVLayxDMXhk0jnfY9MOAdgCR5NAgE4yAeiZoFZHXTKVou5f0xr-jfvNZrKLRtXF6zVU4lgip_UMqYHTJRjkGlMDJRzwwY9fSng6xHQ6pVKiIzqLB1x3m4x5n0ky5QBwrb7iSvHcUjvbw7lVtE-bcx4FJFFfhj1zOAF7y383YCr0h-3w-_PXxvAH_IG7y1)

## 什么是 PlantUml

[PlantUml](http://plantuml.com/)是一个支持快速绘制的开源项目.其定义了一套完整的语言用于实现 UML 关系图的描述.并基于强大的 graphviz 图形渲染库进行 UML 图的生成.绘制的 UML 图还可以导出为图片,以及通用的矢量 SVG 格式文件.

如以下代码，可实现时序图

```
@startuml
Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response

Alice -> Bob: Another authentication Request
Alice <-- Bob: another authentication Response
@enduml
```

![时序图](https://www.plantuml.com/plantuml/img/TSx13O0W38NXErDqWIvWZ057S0F49f9WKIZxIyIJmVFxykVfB3P9EO8omJi2d62Ewm2co4uitbdnaM6Xgr0MLJV0QXxSKVcCd4bzOnohIs3xqOP7nARjdtxZcdYhXsy0)

可以使用常用的编辑器 vscode 或者 sublime 或者其他 IDE 工具继承 PlantUml

也可以使用在线的版本
[https://www.planttext.com/](https://www.planttext.com/)

想了解更多 PlantUml 或者使用方法，可参考官网[http://plantuml.com/zh/](http://plantuml.com/zh/)，上面详细的中英文说明

## 什么是 C4 Model

[C4 Model](https://c4model.com/) 在我眼里更像是一个标准，一个方法论。让架构师、程序员、业务人员在讨论 IT 系统架构时候统一维度，统一标准，更方便的理解和沟通 IT 系统中的真实问题。**强烈推荐**！！！

C4 模型由一系列分层的软件架构图组成，这些架构图用于描述上下文（Context）、容器(Container)、组件(Component)和代码(Code)。C4 图的层次结构提供了不同的抽象级别，每种抽象级别都与不同的受众有关

![C4 Model](https://c4model.com/img/bigbankplc-Containers.png)

这篇 Infoq 的文章是有一个比较详细的介绍[https://infoq.cn/article/C4-architecture-model](https://infoq.cn/article/C4-architecture-model)

## 本库只是一个样式库

本库的目的是美化 PlantUml 和 C4 Model 所绘制系统架构图的样式，统一审美而产生。

详细的使用方法，可参考 sample 文件夹中的示例代码
[https://github.com/xuanye/plantuml-style-c4/blob/master/samples/](https://github.com/xuanye/plantuml-style-c4/blob/master/samples/)

<!--more-->

### 1.时序图

在 PlantUml 代码中引用

```
@startuml sequence-sample
!include https://unpkg.com/plantuml-style-c4@latest/core.puml
' uncomment the following line and comment the first to use locally
'!include core.puml

LAYOUT_AS_SKETCH()
' 设置红色箭头，分图定义有冲突
RED_ARROW
'MEGENTA_ARROW

title <size:20>Sample Sequence</size>

actor User
participant "First Class" as A
participant "Second Class" as B
participant "Last Class" as C

User -> A: DoWork
activate A
note over A: this is a first note
A -> B: Create Request
activate B

B -> C: DoWork
activate C
C --> B: WorkDone
destroy C

B --> A: Request Created
deactivate B

A --> User: Done
deactivate A

@enduml



```

![时序图](http://www.plantuml.com/plantuml/png/PP1FQnD16CRlyobUUuaUqXNnj9IGoIOgM2raKugdCCo-DaDdPzQPTolnvgKOy1Ee9_4ac4FnecW_ZMjwyoiuqousYx2m3B_dppmpz2GSrQLcjvIHkYuG5aILJvEaDjN9yQwqPL9fOQAcxscfiI_l3xKWz9H8wt2tYkuUr2P8IpG4j41uRhMsBvKv1gqCWZ05TB1ode0ir1v1MocqNhBUlolSvB9z_kpWS3Rd-Jn_F9bbZsxV2LsNwulDp_Nc-yVBrVbc_QNvzFNFZxVDcxFc_KMpVlVhs-htXrLpThxv_9fD9-CvdquFZbZloUJXvEcCjqT6YZJ2dbUlCBrtTv2BiWhd75_KQ2Jk9H4C61EIh8D3ZuvLmf6IgXA6OEV1rOHC2-ztG7ZWNPoZjAROugCktnSTTyPOh83-07WAOtjatKciLgU2C6GR6txs55t4j50UmYVQTuoGyUWTfP0vZ9PftE7f9cF4s2XAil_ZCvP1_zeTmTWQP4KmExiCBDgkhzLcjXL5q6odyojPN9526x4rO8Ycg4lz5m00)

### 2. 类图

以下为示例

```
@startuml 示例类图

!include https://unpkg.com/plantuml-style-c4@latest/core.puml
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

![类图](http://www.plantuml.com/plantuml/png/XP31Ilj04CRl-nJpp_zGHT8WU2eXj8f83oBKKl6asysqNPpiXkokKgfFu2DuzGMyAlHfbBw6cpQsJG-QIsRvlldcDzCsbXVMPGIBr_VF-VFYxUFhPSxOFwa4kHHXOcrkMb7aL7utRWgTHJbnLNQ4nau9Gt7K9cxHs4Ze0fkvLrW3dFBM39K5Eq4OQIBz8DKOI2e4hbAeoR8mljBW309fmOcchB56sEIoizxfzKsdrxkuOemFZIsui2286mF7tE39ifenyDy1GATodAETw7Hl7rfmhsMwbFy33AJVd5EbcfOtUyJI9PLbJsoLU-c6zTZVK_yAPVw7nOWBX6xtf-p0h2u5MzhjOH3tashyW9D37zQ7E1wZJP8rPpVB2SkJrcchXdBwLilcMF5Z6AvtPDj8fR8BmdRU4CHIsIHOcUi8ZBLHfIwZRm00)

### 3. 状态图

```
@startuml state-sample
!include https://unpkg.com/plantuml-style-c4@latest/core.puml
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

![状态图](http://www.plantuml.com/plantuml/png/RP6nxjCm48TtFyMnK0cHPc7gW8ggG8UghK8b1eIGbLmJAnSxs6TGUNgScDI4VpRxzvs_krpsZgLbtnE40sFcP3yGYbTAL-HhX9PvSBiyztheccrb-dmWgSS7cUC7OLQzsvDaT9nNnk9s24HimEjGsgDcu1RXReZCBwKR8AKHfAvXWPLruMJ0EmGobIHwYCrpXEGLdygYE7__K9QNBqAmOa8utcvNAF67n-2uIkl6Dfzv74c8hs--GPQzd_afT1SYNH1sqvDe-G_OU9j6Ng1HU4HPetMXxDAzW8MrnWRqKIho5eL8rVzqIs4RJtCI6nZ7qPxIDNCiExHOTT26ovn49oW7WqM7Ee99SaBTS1jgpeQXQhtki4xq48D9cj1wzsXwzbVtQMdAOlqsiP-IL0slmQdVEAShjZLKQ5RyW9inS9AsMTI4Nnlt8zB4QRifZ5_uTnzpl3P0OWlx7dNjU_e3)

### 4. 用例图

```
@startuml usecase-sample
!include https://unpkg.com/plantuml-style-c4@latest/core.puml
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

![用例图](http://www.plantuml.com/plantuml/png/NO-zJW9158NxUOhhDa3YieqLXO4WYf48aIN6QZCPhkncxyvCvYTAZ8zWeeK-1h6bqASHzJ5Sv8TeD-USRqxERLh7ZVC5WRSekCNGya8JihrC2l9ZXDGvRHjHvANE9tMXYaWJbyileNLJmb0SD8axj2uIoc1TbmchW9SbMg1qu5A4QqMaRZ8v0Sea0fTZ-1DdnfOljHm1f0GdchBATiAkjop-dhr_lSq-N-QBnoVMQrtrHt7Iwnp7oSNfIJTcbRKLzmV9KV_oV6kqXidmh1EtkumnBfmo8Bnrga2paOGcPsnaqRIvnG4NEPzWDH0fYbnv5-m77_FNnSDpK8Cx1W3R0WX3g6wmsc-qar0_XAhcqm9bAHgmFcf5fKXwHUpu1k2jGpcs_ul2SBtndh5c2VY2VW00)

### 5. 活动图

```
@startuml activity-new-sample
!include https://unpkg.com/plantuml-style-c4@latest/core.puml
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

![活动图](http://www.plantuml.com/plantuml/png/RLB1ZjiW4Btp5TFJ9eSabvwSIasrsgvwQLVUGuyLmkC4PGoK6JRAtnTCxCgIELXuvht7UmCd5Xqb3GJQYFsmSjyvlErO3u5GVRBEKEeGBYA1cyCXkN0zxuqV3e6qAxmTovrmPpwVI0ko78oFk0-vevuWkGmTq0d81Q7tHFvctHd8EWJjEbYqRUIyyv0OWRpHH7VrD5luhwjUsvUNdt--jUsltqgfCO5gdicQwpl63qBPNx8uOOj_4x9ijaVLv5GGz1cFolQmUSkxlNVlQ5BCcPylQAxRuiB1HcB2hOAycWViXxEZIAaLjkNlFjvqxBvE7EShexAYDyYS7Jk9dhWI9tAfMfSGGeNbUQp8rCNYmrn0rzb-8MNvpRFCx3loaZxvpwZY_ylSH6Aifwt1Nx6Wry-TGMqkOvnm5LDbUqsCMrLBnMRd8M9d8veLhytKckPn76N6teFSrs6lvsmULm6nNlPHhGTigk7n3O3W44WBBioFNpME_9H_qa3_0000)

### 6. 其他组件

```
@startuml element
!include https://unpkg.com/plantuml-style-c4@latest/core.puml
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

![其他组件](http://www.plantuml.com/plantuml/png/LOunRiCm34LtdeATCYLUEdNALHY9TeJGf2jHA7pxIexjeilx3wH4_7jnobvdGHQUMHq-aWQfaV7flfIlOQYwlAPRi7bOXBI_lHPVXQ_XyoxaN7m8blcsj0rSi6fxsY-XFnb74x6Vf1DAKaRIYF_MAPTcXhKmYWKIMU5oLlYx2q31BUD6eAaVs0YKFOrjZ8V0mwf6oYiU0e5on0u8OhLf9xGYYsc_T5gRgMSJt1CYEJseC1u2h9vynNV0c8In0qQJo1dV0MEccN4Z97NEhHaZdWfgaR435WelcXZtXE_AbN4Z56z3t0YPWvDEmdXQsrlkV_U4MZZqjdl2dJNMMNu1)

## C4 模型

### 1.System Context

```
@startuml system-context-diagram

!include https://unpkg.com/plantuml-style-c4@latest/c4_context.puml
' uncomment the following line and comment the first to use locally
'!include c4_context.puml

LAYOUT_WITH_LEGEND()
'LAYOUT_AS_SKETCH()

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

![System Context](http://www.plantuml.com/plantuml/png/VL5DRnen4BtlhvXoWKXyN7Bg2K9NJTIGHeMewcarc04i_B7op1Ruz_KkPWifpSqUl_VclUSn2mQfhCa-QQTCjIBOYfJyUJIgNBdR39MtezAWgp43bgEXWReV6nHY6QdxGdadT91XMMjqeNAHOCa9o9PWxOtnU-qsOBGZGBU2gsSTE9uyL4nWl49ZZbctDV9UFNkU_Fh-jYX-FYqUY-VyQ_xofNUNTTDqCY_ct_B5z37ECj5Y2EP75h8mFOd0IkCce8sk0Zp5KN0ay81k5mqcR9PDbFZGKnMBjnJwq7cbmDwXQP7JzDQ9ZnCu8y6lcqpBYEh3NiiMoiHiPe1A-Se93pjtsMbPRtbIBBYvHhd_k6esrKrokuxhsdvhseDsCOz5qTu1BdtLLAl3zT9-qxt57K69Hql9Hp9Iv0VfMTJchvDyKD-1s_sBc4qtzj30JAlWsQy5yeFQejiGq2MXpTXAktLidgBEx7o-aN4kFX036dDkKyK1f9fk96tRw5yabO2EKTMmU2DHJT8VP2v-zP_ctvWumYAgU42rku1Uzp8dj-8Kba5yuhoGtcoNFhp_qe_OJUBPulKaSOkPIclTZIEzikOF)

### 2. Container

```
@startuml container-diagram
!include https://unpkg.com/plantuml-style-c4@latest/c4_container.puml
' uncomment the following line and comment the first to use locally
'!include c4_container.puml

LAYOUT_TOP_DOWN
'LAYOUT_AS_SKETCH()
LAYOUT_WITH_LEGEND()

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

![容器图](http://www.plantuml.com/plantuml/png/bLJ1RkCs4BthAwRf8Lv0YL5WJpt5iOqcspXnLzvcUn96rDWcGf42EKhMAFhl7IgoP2KBR7kJHZFlFRvvr5LWzDnK1fIpZDgIloWrxZnMoK_QAjEK17lcElmwdJQsVjfTAbTDQuCsJbq4FXYwK1-l3385dggFUGzqMKj7SWwDbP6AB0Fl2RRE6FUYxGwCD07Q4aQVjG_ovA091COfDEQGdFTItkCdTxE_7hviyit3EbyyFDudvrrXbkNPxylD_6RouTZpUBkvoU-Mlotl5r9CMBCXc1_ne3kuIFHmQvcy9OPhj4zHRNO8J5MIp1GxFr5DO5UHJs7UFvtDu5W6jsrFKyXm2Y-Qzr2J3ywYQMk0Ihd6SZWJ6Q_8-RKKIlI7YVf5iDxodts0lnC06EHENgZ8iQwb-P4AcDMrqGfPEticfK_uZ2bajO_QLt_EOsr1HZ-BZ5PQOEbLxTh9Shk7MEvvY-EvrpCHEMOEDGfS9fzb-MlSKMG_icRAwvfJcDbTOz37yjgxPrrI03Jc-onR2KcKZaRp8QvVDQsH0PurnX7jGSuBXNSlWVmxHPKhjA7EZbLywJNDVqxXArOeJeorWD6LPYeXD4KWbftzPstXdRXN0L3IirRqLjwYc9J8M62Wk8RkCQh9_hY3qJixJo66tuEddGxiKQX1MmbbrMutXJq6KOqDxq5vAicoHXFI62eA0OpRoGknkdndKu7gYMmfFkcOr_NjzsEpSDBcXxcHRp_m9reYm4BzJn_jvJUUK8NQvA4j2DpoOYNltQsA-1knNhVGQ62bbNV1RHcMtzGUxOxWTL9WJp0x1GEgODgjnuhUNDiJQz6OuwQL5FfJd3WCMBY6XpMd_NLDWJtQWErv1vEJpsHEVWd3nVmIA4JkcyrcdKdZk2_K-CEUKR1ZQqUNtvFUxGlN_mOwkFwITqXjSRJsdX33mQeKFcKFzzDJye7oVqxcrz8z21iYFqRvJ5W6s7fNjN-T5w-P0h2Bo1tmudeka3tcYHzlOfG9R02wYDKMOn0oIjn8mxkv9aW21lfijLaBqCZbqVWuTuCnxVoqS-Vhwgutvqf6cyhy2m00)

### 3.Component

组件图

```
@startuml component-diagram
!include https://unpkg.com/plantuml-style-c4@latest/c4_component.puml
' uncomment the following line and comment the first to use locally
'!include c4_component.puml

LAYOUT_WITH_LEGEND()
'LAYOUT_AS_SKETCH()

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

![组件图](http://www.plantuml.com/plantuml/png/fPHDK-D648Rl-XKT3i5K0RxiAIUC8O4Dx5B8cu-JgpLgv0dpePeUuRXI-U_f6SkI3LIAgZrfrFDEzpDljtJ14KFih07bRUiTkNXMQsm2sk87xPJfQe9LZ2t_D9rshdrkpaKuRGswTEgCuyRGcVfqOJ0Inwdwj1mIdRUYA8wXSnAo4e2u8dZonlYrTWqOxGZGrN2mhGFBoaF71COhD6PJ70yeR_CNTxC_ltvRB7-_NTmixwv_kVvoDJafZlleh5oMlrulvZSIAwAEXc2-Em_zHGKfmAsB51n5k4JtdEZA3KUoS0QpXrkOjQtH2gFshYZctaKKzZ3X5a_Xg1Ivv7t0XlQ5HxBr5xuWgw3Rc2-AhkaCXhJp4FoBhea1ZSaNrpk0gWTu4jzI7ZGwRf8ZgkFeBGM65utfZ0wmfWgguDTCuVpeP0_D9h9xNscJeLB9Fz1YqEwmEXXjTQGQkAkO8lZu7JGsrzizQdhHYWwmhgf9NKdzAunO8LDYUII3syom2qEfLcGnxPRH1-8q3G42DPfZo6eXbBRPl3w55VAAQi1EE5pi6m0gK9rUqV0fe5B43COtya9H9QvjZvVNVyU9hJWPXf8seALNOp2Iv7xvfsoIai1Wq1uFOEMxE3gKY_lEHLa9lcFCLeuSeq7BIz7L63OJRBKKVJLyHoVmJm40un1FM3SkqSb3XXXIfk2DeJnbzx_DuP4uZk4KdQKlSEiffrQc5C8lo_TxpriFJbvL7Yub6Vibb9srGlyHZ748nr5QwxW219OiFcnwdtN898E9Rq2OL1TaB9CD_NBSpQrhGxh79U7Xz1yETKY3I7LsHEJRffw2Mk7sfKNcjG_rsBT335ln4ogiwNy62NxEYdUWPh0z3DxrVR13ZiD6fCgvz2EPllrx3dnZ4eU6_R598zuRqNYyhl8NYJNy26i94KIVw3vVNSxt3kpbacMVCFzZxk-cDul5GodYVuiYQVDFCcEEii_bro-3RX2DhEyBiz9-89lzIB8BSdLdpNy0)

### 4 Code

类图上面已经演示过了

### 5. 扩展图

```
@startuml system-context-extend-diagram
!include https://unpkg.com/plantuml-style-c4@latest/c4_context.puml
' uncomment the following line and comment the first to use locally
'!include c4_context.puml

'LAYOUT_TOP_DOWN
'LAYOUT_AS_SKETCH()
LAYOUT_WITH_LEGEND()

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

![扩展图](http://www.plantuml.com/plantuml/png/VLF1Ri964BtxAwPSGYG8FUJKKo2W9Ye9KI2AUhAMzHYlME-wE-CGLFNVksjiroRG0n8xy-RDUpFZ1sBXkCmrq94Oyx6qXl6Rn_w79XadIkoSoADVb96wJ10ove9-cqnAK-ntTzBcaq8B4nZ6n4UDOtd_e0KZyKJUnpNRNU7pqGsKnXVaQ1WuGqYjrlQWp0wqCWZ29D1BAqSCRA4a16sbqFeOtRH2pjcZc-NqpzN79jwitkBvwlEr3KpNyVgFnURnQNWRrQ7FvyrJl5pyldYT-s34YZN2kfe0BBqGag90gCrxeGvcQWSpOVPGQ1b5KydM3ML9R7Dq8nYyeIDhXAummT9ZdHluv1GQ9DYqyhRrg14S56TGD9KX1a9AMngcku6NjJ2Chd2AC9xvQ2BSSIX_zOHTCODR-3i2W5h-S7iI45FrzE3dm6AG6sari18M5a2jEWhJ_b9u06MyvromiWR4rfRLHfJhQnnLAyl57g4GnnnhsHqnyUARXuBpq6hpSgrZ64FYn06aeCmpd1FaGkd_x2p6uGtKcjXa2AhoA3IyAEaisPHXyIqpONO8s2su9D2dJUf4ZfxifVb_OLfhjWu9XDRD6gKFG3tm2pDhNOuwCsCd30aPOFw5B5j9fnkg93MLCQ7xKZ8eQmuArgSGh5cawQ2RgS508LEDLPdst7oRyovR8VUnJTDJWvb_mSg_kjpJ95T64RlQbqc0ogAmZgzt-IUAtb77hwXssRRtcVoupGz2yXK1_jx1dKxcixuBgWu3IlAbDJXexU3x5x96ar2zzd1WlkP7Xmi3djAUuAyIAJYjwi9neSOYimORaldP1_P_pNkItqyVGlVOkkxxjDU1ymktSGNwqIxu6YfQYgDdh8Jr-_TpJSlR4FIy7SlTPFJWpPUv_XS0)

## 参考

C4 Model 的配色和实现大部分都是直接使用
[https://github.com/RicardoNiepel/C4-PlantUML](https://github.com/RicardoNiepel/C4-PlantUML)的,只有几个配色略有调整，并抽取出颜色的文件，可单独替换 c4_theme 以实现其他配色
