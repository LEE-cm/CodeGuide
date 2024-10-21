---
title: 第五阶段完结，微服务对接
lock: no
---

# 第五阶段完结，微服务对接

作者：小傅哥
<br/>博客：[https://bugstack.cn](https://bugstack.cn)

>沉淀、分享、成长，让自己和他人都能有所收获！😄

大家伙，我是技术UP主小傅哥。

哎，你这一个电商/点评项目，一个营销活动项目，怎么没有两个项目的对接。你的营销活动可以给你的电商提供抽奖、积分、返利、兑换等等，但为啥都是独立存在的？你有思考过他们是怎么对接的吗？

<div align="center">
    <img src="https://bugstack.cn/images/article/project/big-market/big-market-v8-01.gif" width="200px">
</div>

**那微服务的对接，你有经验吗？**

没有🤔？没关系，小傅哥为你实打实的提供两套微服务项目的对接使用，包括；后端对接、前端对接，以及不同方式的接口形式对接方案。在这个过程中让你搞懂，这些微服务的对接思路、方式和落地手段。有了这些经验后续你也可以把这样的微服务，衔接到各种项目了上了。让你的项目成为一个蜘蛛网🕸一样的微服务布局。

本篇文章提到的两套微服务分别是；`OpenAI 应用项目`、`大营销系统服务 - 抽奖、积分、兑换、返利`，这两套微服务都是小傅哥在星球「码农会锁」为大家提供的实战项目，本节为大家提供出对接方案和效果。非常提高综合实战能力。

> 文末有加入学习方式，可以获得整套课程的；视频、文档、代码、面试题、简历模板等。

## 一、项目简述

- **OpenAi 应用项目**：前后端+Dev-Ops，全栈技术实践。以OpenAi场景，运用DDD架构，实现从微信公众号扫码登录，到下单支付对个人账户充值，完成 OpenAi 控制敏感词过滤以及多渠道策略模型的对话消费的全流程。
- **大营销平台系统**：前后端+Dev-Ops，全栈技术实践。项目将先以最新DDD架构和模式进行重构Lottery项目，扩展用户、账户、积分、兑换、分享模块，以及和 OpenAI 进行微服务整合，RPC/HTTP 通信完成项目综合使用。

>项目演示地址：[https://gaga.plus](https://gaga.plus) - 你可以直接在线查看项目的演示运行效果。这些项目都是企业级的设计和实现，远比简单的 CRUD 那种 DEMO 项目要牛皮的多！

## 二、对接方案

OpenAI 应用项目，提供了`支付购买对话额度`的服务。那么我们为了促进用户在 OpenAI 项目上的使用粘性，就可以添加营销模块。让用户在完成`每日签到和支付`后，就可以获得相应的积分，再通过积分兑换抽奖次数完成抽奖。抽奖有机会获得不同级别的`对话额度`赠送。以此完成用户行为旅程循环。

<div align="center">
    <img src="https://bugstack.cn/images/article/project/big-market/big-market-v8-02.png" width="650px">
</div>

- OpenAI 前端应用，通过 Nginx 负载，HTTP 方式调用 OpenAI 后端和大营销后端服务。完成前端的UI的业务流程串联。
- OpenAI 后端应用，在支付完成后，调用大营销的返利接口。大营销可以配置完成某个用户行为动作后对应给到积分或者抽奖次数。这个对接可以是 HTTP 或者 RPC 对接。
- 大营销平台系统，在抽奖的时候增加 OpenAI 额度奖品。也就是抽奖后可以给一个n次数的对话额度，所以大营销需要对接到 OpenAI 提供的 HTTP 接口，处理额度奖品发放操作。

## 三、对接效果

OpenAI + 大营销，这是一套综合`前后端 + DevOps`的全体系技术实战项目。采用 DDD 架构设计落地，运用设计模式编写整洁的代码实现。结合 OpenAi 技术、微信支付渠道、敏感词过滤、营销积分、兑换、返利的综合玩法项目。

### 1. 营销页

<div align="center">
    <img src="https://bugstack.cn/images/article/project/big-market/big-market-v8-03.png" width="650px">
</div>

- 在 OpenAI 页面，增加营销活动模块，展示出用户的额度、积分、签的到、抽奖次数。以及抽奖和奖品兑换操作。
- 这些内容都是可以通过配置完成的，调整用户的获得积分的大小、以及兑换商品是的价值，再有就是抽奖的概率配置。可以非常灵活的调整，让用户非常喜欢这样一套产品。

### 2. 支付页

<div align="center">
    <img src="https://bugstack.cn/images/article/project/chatgpt/chatgpt-extra-231007-07.png" width="650px">
</div>

<div align="center">
    <img src="https://bugstack.cn/images/article/project/chatgpt/chatgpt-extra-231007-08.png" width="650px">
</div>

- 用户可以通过下单支付的方式完成商品的购买，购买后就可以对购买支付的回调，进行返利积分或者抽奖额度。
- 星球的课程体系还提供了，微信支付、支付宝沙箱、蓝兔支付，多种方式都可以按需使用。

> 关于项目的更多了解：[https://bugstack.cn/md/project/chatgpt/review.html](https://bugstack.cn/md/project/chatgpt/review.html)

## 四、加入学习

小傅哥的星球「码农会锁」提供了一整套的实战项目学习进阶路线，从小白到大佬，全程视频手把手带着从0到1，一步步完成项目的设计、开发和上线。在整套内容学习过程中，小傅哥为你提供了非常好的技术交流社群，及时解决学习问题。还包括调试你的问题代码，带你快速🔜出坑！

<div align="center">
    <img src="https://bugstack.cn/images/article/zsxq/zsxq-241007-02.png" width="450px">
</div>

- 首先，这一整套全体系的学习课程比私教培训实惠，更比培训班上万的培训费便宜。可能也就是培训班1天的💰钱，就能学习到这一整套内容了。
- 之后，你学习的整套课程，就是小傅哥这个架构师自己全部原创编写的。这也就是说，你所提到的任何问题，小傅哥都能给你解答和讨论。
- 那么，这么实惠的课程，成体系的课程，还是架构师编写的。还有什么可犹豫的，完全可以撸起来了！