---
layout: post
title: Introduction of SE & OOAD
date: 2018-03-13 19:35:00 +0800
tags: [Software Engineering, Terminology]
---
# Introduction of SE & OOAD

Thanks to [Wikipedia](https://en.wikipedia.org) & 《人月神话》.

Note:

- Not all of the Chinese version are translation from English.
- Some terminologies have just English/Chinese explanations because:
  - Not all terminologies have proper explanations both in English and Chinese.
  - One of the two is a simple transliteration from the other (and too long).

## Simple Question

### Definition of Software Engineering

"the systematic application of scientific and technological knowledge, methods, and experience to the design, implementation, testing, and documentation of software" -- IEEE Systems and software engineering

"The application of a systematic, disciplined, quantifiable approach to the development, operation, and maintenance of software" -- IEEE Standard Glossary of Software Engineering Terminology

"应用计算机科学理论和技术以及工程管理原则和方法，按预算和进度，实现满足用户要求的软件产品的定义、开发、和维护的工程或进行研究的学科"。 -- GB/T11457-2006《信息技术 软件工程术语》

Note: The latter English expression is somewhat more similar to the Chinese one.

### Software Crisis 软件危机

**Software crisis** is a term used in the early days of computing science for the difficulty of writing useful and efficient computer programs in the required time. The software crisis was due to the rapid increases in computer power and the complexity of the problems that could not be tackled. With the increase in the complexity of the software, many software problems arose because existing methods were insufficient. -- from [Wikipedia](https://en.wikipedia.org/wiki/Software_crisis)

**软件危机** 是早期计算机科学的一个术语，是指在软件开发及维护的过程中所遇到的一系列严重问题，这些问题皆可能导致软件产品的寿命缩短、甚至夭折。软件开发是一项高难度、高风险的活动，由于它的高失败率，故有所谓“软件危机”之说。软件危机的本源是复杂、期望和改变。这个术语用来描述正急遽增加之电脑的力量带来的冲击和可能要处理的问题的复杂性。从本质上来说，它谈到了写出正确、可理解、可验证的计算机程序的困难。

软件危机其原因，衔接到硬件的整体复杂度，与软件开发流程。危机表现在几个方面：

- 项目运行超出预算。
- 项目运行超过时间。
- 软件质量低落。
- 软件通常不匹配需求。
- 项目无法管理，且代码难以维护。

硬件成长率每年大约30％，软件每年只勉强以4～7％速度在成长，信息系统的交付日期一再延后，许多待开发的软件系统无法如期开始。1960年代软件开发成本占总成本20％以下；1970年代软件成本已达总成本80％以上，软件维护费用在软件成本中高达65％。1986年公布的数据，所有验收的外包软件中，竟然只有4％可用，其余96％却是不堪一用。大部分的企业自行开发的信息系统中，有四分之三也是功败垂成。因此软件维护成本居高不下，软件产品质量低落是最主要的原因。

### COCOMO model 构造性成本模型

**COCOMO** from [Wikipedia](https://en.wikipedia.org/wiki/COCOMO).

Basic COCOMO compute software development effort (and cost) as a function of program size. Program size is expressed in estimated thousands of source lines of code (SLOC, KLOC).

COCOMO applies to three classes of software projects:

- Organic projects - "small" teams with "good" experience working with "less than rigid" requirements
- Semi-detached projects - "medium" teams with mixed experience working with a mix of rigid and less than rigid requirements
- Embedded projects - developed within a set of "tight" constraints. It is also combination of organic and semi-detached projects.(hardware, software, operational, ...)

The basic COCOMO equations take the form

- Effort Applied (E) = a_b(KLOC)b_b [ man-months ] ("a_b" means "a with subscript b", same as below)
- Development Time (D) = c_b(Effort Applied)d_b [months]
- People required (P) = Effort Applied / Development Time [count]

where, KLOC is the estimated number of delivered lines (expressed in thousands ) of code for project. The coefficients ab, bb, cb and db are given in the following table (note: the values listed below are from the original analysis, with a modern reanalysis[4] producing different values):

| Software project | a_b | b_b | c_b | d_b |
| :------| ------: | ------: | ------: | ------: |
| Organic | 2.4 | 1.05 | 2.5 | 0.38 |
| Semi-detached | 3.0 | 1.12 | 2.5 | 0.35 |
| Embedded | 3.6 | 1.20 | 2.5 | 0.32 |

Basic COCOMO is good for quick estimate of software costs. However it does not account for differences in hardware constraints, personnel quality and experience, use of modern tools and techniques, and so on.

**Intermediate COCOMO** computes software development effort as function of program size and a set of "cost drivers" that include subjective assessment of product, hardware, personnel and project attributes. This extension considers a set of four "cost drivers", each with a number of subsidiary attributes:

- Product attributes
  - Required software reliability extent
  - Size of application database
  - Complexity of the product
- Hardware attributes
  - Run-time performance constraints
  - Memory constraints
  - Volatility of the virtual machine environment
  - Required turnabout time
- Personnel attributes
  - Analyst capability
  - Software engineering capability
  - Applications experience
  - Virtual machine experience
  - Programming language experience
- Project attributes
  - Use of software tools
  - Application of software engineering methods
  - Required development schedule

**Detailed COCOMO** incorporates all characteristics of the intermediate version with an assessment of the cost driver's impact on each step (analysis, design, etc.) of the software engineering process.

The detailed model uses different effort multipliers for each cost driver attribute. These Phase Sensitive effort multipliers are each to determine the amount of effort required to complete each phase. In detailed cocomo, the whole software is divided into different modules and then we apply COCOMO in different modules to estimate effort and then sum the effort.

The effort is calculated as a function of program size and a set of cost drivers are given according to each phase of the software life cycle.

A Detailed project schedule is never static.

The Six phases of detailed COCOMO are:

- planning and requirements
- system design
- detailed design
- module code and test
- integration and test
- Cost Constructive model

### Software Development Life Cycle (SDLC) 软件生命周期管理

软件生命周期（Software Development LifeCycle）是指软件的产生直到成熟的全部过程。

生命周期是事物发展的客观规律，软件同样存在生命周期。早期的软件生命周期往往是说“软件从计划、需求开始，经历分析设计、实现、部署、维护，直到最后逐渐消亡的”。这是受到了第一个软件生命周期模型---瀑布模型[1]影响，上述语句实质上简要的描述了瀑布型生命周期。 现在的软件生命周期不再只考虑瀑布型生命周期，另外常见的软件生命周期模型有原型模型、螺旋模型[2]、迭代模型。所以现在的软件生命周期说明应当不再包括瀑布型生命周期中的典型阶段。

因此，现在对软件生命周期及软件生命周期模型采用如下定义：

软件生命周期是指软件的产生直到成熟的全部过程。
软件生命周期模型是指人们为开发更好的软件而归纳总结的软件生命周期的典型实践参考。
最近几年来，给软件生命周期带来最多活力的是敏捷软件开发，使得这个领域呈现出勃勃生机，出现了一些更好响应变化、迎接竞争的生命周期模型。

敏捷软件开发明确对生命周期模型提出了要求：短迭代开发。迭代模型的历史可以追溯到上世纪50年代，但以往的迭代模型并没有对迭代周期长度提出要求。而在敏捷软件开发中，迭代周期长度一般不超过2个月，而常见的迭代周期是2周到4周，因此可以称之为“短迭代”。

有些敏捷软件开发在主开发过程前安排有预研或计划或架构或需求阶段等等，在主开发过程后安排有系统集成测试或验收测试或试运行等等，这样做并不违反敏捷开发原则，但其主开发过程应当采用短迭代开发，而且主开发过程的工期应当占有显著的比例，形成多个短迭代。

敏捷开发讲究固定的节奏，建议按照固定的节奏开发，所以短迭代的周期长度在开始选定之后，一般不作改变。同样的原因，敏捷迭代与迭代之间一般不安排缓冲期，上个迭代未完成的内容放到下个迭代中进行处理。

敏捷开发迭代与瀑布生命周期的阶段是不同的。瀑布型中需求分析阶段的产物一般是需求规格说明书，不同阶段的产物是不同的；而敏捷开发迭代的产物是软件本身，前期迭代的产物也许不完整，但各个敏捷开发迭代的产物是一致的、逐步改进完善的软件本身。

### Which KAs (or areas) are mainly concerned according to the KA-division of SWEBok

ACM与IEEE Computer Society联合修定的SWEBoK（Software Engineering Body of Knowledge）提到，软件工程领域中的核心知识包括：

- 软件需求（Software requirements）
- 软件设计（Software design）
- 软件建构（Software construction）
- 软件测试（Software test）
- 软件维护与更新（Software maintenance）
- 软件构型管理（Software Configuration Management, SCM）
- 软件工程管理（Software Engineering Management）
- 软件开发过程（Software Development Process）
- 软件工程工具与方法（Software Engineering Tools and methods）
- 软件质量（Software Quality）

### 5 Levels of CMMI

能力成熟度模型集成（CMMI）是一个过程改进方法，它的目的是帮助组织改进他们的绩效。CMMI可以被用于引导横贯一个项目、一个部门或一个完整的组织的过程改进。

![CMMI]({{site.base_url}}/assets/img/Characteristics_of_Capability_Maturity_Model.png)

Level 1 - Initial：无序，自发生产模式

事实上，由于第一级“初始级”是组织的初始状态（可以认为每一个没有通过CMMI评估的公司或组织都处于“初始级”），故成熟度级别评定从2到5级。

CMMI-开发方面：（服务、采购方面略有不同 [Wikipedia](https://zh.wikipedia.org/wiki/%E8%83%BD%E5%8A%9B%E6%88%90%E7%86%9F%E5%BA%A6%E6%A8%A1%E5%9E%8B%E9%9B%86%E6%88%90)）

- Level 2 － 已管理 (Managed)
  - CM - 配置管理（Configuration Management）
  - MA - 度量和分析（Measurement and Analysis）
  - PMC - 项目监控（Project Monitoring and Control）
  - PP - 项目计划（Project Planning）
  - PPQA - 过程和产品质量保证（Process and Product Quality Assurance）
  - REQM - 需求管理（Requirements Management）
  - SAM - 供应商协议管理（Supplier Agreement Management）
- Level 3 － 已定义 (Defined)
  - DAR - 决策分析和决议（Decision Analysis and Resolution）
  - IPM - 集成的项目管理（Integrated Project Management）
  - OPD - 组织级过程定义（Organizational Process Definition）
  - OPF - 组织级过程聚焦（Organizational Process Focus）
  - OT - 组织级培训（Organizational Training）
  - PI - 产品集成（Product Integration）
  - RD - 需求开发（Requirements Development）
  - RSKM - 风险管理（Risk Management）
  - TS - 技术解决方案（Technical Solution）
  - VAL - 验证（Validation）
  - VER - 核查（Verification）
- Level 4 － 已量化地管理 (Quantitatively Managed)
  - OPP - 组织级过程绩效（Organizational Process Performance）
  - QPM - 量化的项目管理（Quantitative Project Management）
- Level 5 － 优化中 (Optimizing)
  - CAR - 因果分析和决议（Causal Analysis and Resolution）
  - OPM - 组织级绩效管理（Organizational Performance Management）

### Give a description on SWEBok or CMMI by yourself

## PSP: Personal Software Process

PSP2.1

- Planning 计划
  - Estimate 估计任务需要的时长
- Development 开发
  - Analysis 分析需求
  - Design Spec 生成设计文档
  - Design Review 设计复审(和同时审核设计文档)
  - Coding Standard 代码规范
  - Design 具体设计
  - Coding 具体编码
  - Code Review 代码复审
  - Test 测试
- Record Time Spent 记录时间花费
- Test Report 测试报告
- Size Measurement 计算工作量
- Postmortem 事后总结
- Process Improvement Plan 提出过程改善计划

### What will a software-engineer do when he/she receives a task? What skills required? How to collect the data？

Estimate,

Analysis, Design the doc (by self & with mates), Set coding standard, Design detailedly, Coding hand, Code Review, Test

Record Time, Test & Measurement, Postmortem, and an improvement plan.

Collecting data: will record them in a sheet (like PSP2.1).