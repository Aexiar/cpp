---
# 官方文档相关配置：https://vitepress.dev/reference/default-theme-layout
layout: home # home 是首页，doc 是文档页，page 无样式的文档，自定义页面
home: true

# 官方文档相关配置：https://vitepress.dev/reference/default-theme-home-page
lang: zh-CN
title: 许大仙的博客
titleTemplate: 系统学习 C/C++ 与计算机基础
editLink: true
lastUpdated: true

# 指定要为当前页面注入的额外头标签。将附加在站点级配置注入的头标签之后
head: 
  - - meta
    - name: description
      content: 为知笔记，系统整理 C/C++、数据结构、计算机组成原理、操作系统与计算机网络知识
  - - meta
    - name: keywords
      content: 许大仙，许大仙的博客

# 网站的居中文案
hero: 
  name: "C++"
  text: "从基础语法到工程实践"
  tagline: ""
  image:  # text 和 tagline 区域旁的图片
    src: /logo.svg
    alt: "为知笔记"
  # 按钮相关
  actions:
    - theme: brand
      text: "🏠首页"
      link: "/"        
    - theme: alt
      text: "🎉快速开始"
      link: "/guide"

# 按钮下方的描述
features:
  - icon: 🧠
    title: "建立解题思维"
    details: "从模仿、枚举到分治与动态规划，逐步沉淀可迁移的问题分析方法。"
  - icon: ✍️
    title: "掌握工程方法"
    details: "理解缓存、索引、事件、回调与消息循环，掌握常见机制背后的设计逻辑。"
  - icon: 🚨
    title: "关注关键边界"
    details: "重视边界条件、等价类、数据一致性、死锁与空转，写出更可靠的程序。"
---

