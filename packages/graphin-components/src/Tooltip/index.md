---
title: Tooltip 提示框
order: 1
group:
  path: /interaction
  title: 交互组件
  order: 0
nav:
  title: Components
  path: /components
  order: 1
---

# Tooltip

Tooltip 提示框是一种快速浏览信息的交互组件，常用于图的节点和边上。通过鼠标悬停在节点或边上时，出现一个提示框，鼠标移出节点则取消提示框。这在快速查询元素详细信息时非常有帮助。

## 内置组件：<Tooltip.Node /> <Tooltip.Edge />

<code src='./demos/index.tsx'>

<API src='./index.tsx'>
<API src='./Node.tsx'>
<API src='./Edge.tsx'>

## 开放组件：集成 Antd 的 Popover 组件

<code src='./demos/Antd.tsx' />

## ⚠️：集成 Antd 的 Popover 组件，监听不到 ContextMenu 事件

因为我们集成 Antd 的 Popover 组件，需要一个触发的 DOM，而触发的 DOM 恰好覆盖了节点，因此，我们再引入 Graphin 的 ContextMenu 组件，则没办法监听'node:contextmenu'事件。临时方案如下：在 AntdTooltip 的组件中，监听触发 DOM 的`onContexmenu`事件，自定义 ContextMenu

<code src='./demos/AntdWithContextMenu.tsx' />

## 功能特性

- Tooltip 作为容器组件，给内部的组件提供事件唤起和坐标定位功能,提供 Node 和 Edge 两种容器
- 内容展示组件 完全由用户决定

## 参考资料

> 欢迎 github 的伙伴 讨论设计和组件方案，开源共建。

## 用法

```tsx | pure
import React from 'react';
import ReactDOM from 'react-dom';
import Graphin, { Utils } from '@antv/graphin';
import { Tooltip } from '@antv/graphin-components';
// Do not forget to import CSS

const App = () => {
  return (
    <div className="App">
      <Graphin data={Utils.mock(10).graphin()}></Graphin>
    </div>
  );
};

const rootElement = document.getElementById('root');
ReactDOM.render(<App />, rootElement);
```
