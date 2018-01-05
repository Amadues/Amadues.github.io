---
layout: archive
title:  "可视化 笔记"
date:   2018-1-3 22:07:50 +0800
modified:
excerpt: "学习笔记"
tags: []
image:
  feature: note.gif
  teaser: note.gif
---

# Tableau使用小知识
### 自动创建视图
```
通过“双击”的方式来自动生成，该方法称为“自动双击”。双击所需字段，Tableau会自动将各字段添加到
视图中。
```
- 文本表：先添加维度
- 条形图：先添加度量再添加维度
- 折线图：先添加度量再添加日期
实线图：先添加连续维度再添加度量。添加维度的后续操作是进行细化，添加度量的后续操作是添加定量轴
- 散点图：先添加一个度量再添加一个度量。添加维度的后续操作是进行细化，添加度量的后续操作是创建散点矩阵。
- 地图：如果添加地理区域字段，则会生成一个地图视图，其中包含维度和经度这两个轴，而地理区域字段位于“详细级别”的功能区上，添加维度的后续操作会添加行，添加度量的后续操作是通过添加大小和颜色编码来进一步细化地图。

### 连接数据源
有实时和提取两种方式连接数据源。实时：适合数据量较小，数据实时更新的情况。提取：将数据抽到内存中，生成.tde文件，要更新数据，当报表publish到server上可以设置数据源的刷新Schedule。数据源右上角有一个筛选器，点击“添加”对数据进行筛选，类似自定义SQL中的where条件。数据源是可以多表关联的，默认内联。

### Grop（组）与Set（集）
- Group是维度的组合。如苹果，梨子，桃子，衬衫，T裇，短裙。分为两个Group，水果和服饰。维度一般放在Rows上，按住Ctrl或Shift键同时选择视图中的苹果，梨子，桃子右键单击选择“组”，可以“编辑别名”实现重命名。
- Set是定义数据子集，可基于计算条件。实质上是一个逻辑值

### 发布
- 发布工作簿就是将数据视图发布到Tableau Server。可以选中某些视图添加到服务器项目，隐藏某些工作表，可添加标记增强可搜索性，指定权限以控制服务器上对工作簿的访问，以及选择嵌入数据库密码以便在Web上进行自动身份验证。
- 嵌入式密码——当Tableau Server用户加载视图时，服务器运行身份账户将用于自动对用户进行身份验证，服务器运行身份账户是由Tableau Server系统管理员配置的。管理员可以使用服务器“维护”页面上的“设置”来允许作者嵌入密码。

### 标记的堆叠
```
给定视图中控制标记是堆叠还是重叠。“分析”—“堆叠标记”。默认是自动，也可以手动选择“开”/“关”。
```
- 堆叠条视图
> 维度在列，度量在行，按维度对数据进行颜色编码。标记类型是条，Tableau自动堆叠，这意味着标记合并回执，每个条中每个堆叠区段的高度表示该区段的值。如果解除标记堆叠，标记全部从水平轴开始，但是仍可查看单个条区段。值得注意的是，由于解除堆叠的标记会重叠，因而视图中的条区段可能隐藏在其他区段后面。
- 显示字段标签，“分析”—“表布局”—“显示行字段标签”/“显示列字段标签”

### 使用多个维度
- 每个度量创建单个轴。将度量拖到“行”和“列”功能区来为每个度量添加单个轴
- 两个度量共用一个轴。拖动一个度量或轴并将其放在现有轴上
- 双轴，其中有两个在同一个区中分层的独立轴。双轴是相互层叠的独立轴。若要添加度量作为双轴，只需将字段拖到视图右侧并在看到黑色虚线时放置，也可以在该度量的字段菜单中选择“双轴”。使用双轴时，可以通过右键单击“双轴”并选择“同步轴”来使得两个轴对齐。