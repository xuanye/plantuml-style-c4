## Plantuml的一个清凉主题



![流程图](https://user-images.githubusercontent.com/756204/224526364-1387442c-08a7-44e4-8947-b5d2c6f621da.png)

![时序图](https://user-images.githubusercontent.com/756204/224526445-278d86a0-45cf-4151-9339-e6d90c0e8468.png)

![类图1](https://user-images.githubusercontent.com/756204/224526482-fc07f9b5-9a24-4d9a-9e26-3acde979dba9.png)

![类图2](https://user-images.githubusercontent.com/756204/224526491-f9ca1e3e-2563-454f-84da-e21a0c349d89.png)


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


## 原C4模型主题不再支持，请使用官方标准库的示例
