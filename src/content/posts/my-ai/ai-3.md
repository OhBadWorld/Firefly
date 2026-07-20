---
title: "ai在前端领域展示的场景问题解决方案02"
published: 2026-03-13 22:48:03
# image: ../imgs/algorithms/sucai202203111212.png
coverWidth: 1200
coverHeight: 520
tags: [前端, ai]
category: ai
draft: false
---

# 从前端角度解读Ai相关概念，RAG、Agent、Function call、MCP、Skills 这几个 AI 核心概念，以及它们之间的关联关系，结合前端落地场景说明。

考察点

- AI 核心概念
- 前端角度理解概念
- AI 应用全链路开发经验

## 核心概念

- RAG(Retrieval-Augmented Generation 检索增强生成)，先检索用户私域 /外部知识库的精准资料，再把资料注入上下文让大模型回答，核心解决大模型幻觉、知识过时、私有数据无法接入的问题，前端最常用的 AI落地能力
- Agent(智能体)，以大模型为核心大脑，能自主思考、制定执行计划、调用工具、循环迭代，一步步完成复杂任务的智能程序，是前端 AI 高阶应用的核心载体
- Function call、Tool(工具调用)，大模型按照标准格式，自主判断并调用外部接口/函数的能力，比如前端场景中调用査天气、查订单、查询数据库的接口
  是 Agent 连接外部能力的核心方式
- MCP(Model Context Protocol模型上下文协议)，大模型和外部系统、工具之间通信的统一标准协议，相当于 AI应用的"US8 接口"，一次适配就能快速对接各种工具、数据源，大幅降低前端对接多工具的开发成本
- SkiLs(技能)，提示词+脚本，把高频复用的 AI 能力封装成标准化、可插拔的技能模块，比如代码生成、文档总结、图表生成、内容润色等，相当于 AI 应用的"功能插件"，开箱即用

## 关系

用户提问→Agent任务规划一知识库 RAG 检索→Function Call 调用外部工具→ skills →)MCP
→完成用户需求

tip: MCP怎么做，skills怎么做
