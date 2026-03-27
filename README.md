# Simplerjiang.WinFormAutoSize

[![NuGet](https://img.shields.io/nuget/v/Simplerjiang.WinFormAutoSize)](https://www.nuget.org/packages/Simplerjiang.WinFormAutoSize/)
[![Downloads](https://img.shields.io/nuget/dt/Simplerjiang.WinFormAutoSize)](https://www.nuget.org/packages/Simplerjiang.WinFormAutoSize/)

一个用于 **WinForms 窗体与控件自适应缩放** 的轻量类库，适合在窗口尺寸变化时保持控件位置和大小的整体比例。

English summary: a lightweight WinForms auto-resize helper for scaling controls when the form size changes.

## 项目定位

这个库主要解决的是传统 WinForms 项目里很常见的问题：

- 窗体放大后控件布局失衡
- 嵌套控件缩放不一致
- DataGridView 在缩放后列宽体验变差

它保留了非常直接的 API，用最小接入成本解决窗体缩放问题。

## 目标框架

- `.NET Framework 4.5`

## Package

NuGet: <https://www.nuget.org/packages/Simplerjiang.WinFormAutoSize/>

## 当前能力

根据源码，`AutoSizeFormClass` 具备以下能力：

- 记录窗体及其控件的初始位置与尺寸
- 递归处理嵌套控件缩放
- 在窗口大小变化时按比例调整控件位置与尺寸
- 针对 `DataGridView` 自动调整列宽模式

## Quick Start

```csharp
using Simplerjiang.WinFormAutoSize;

private readonly AutoSizeFormClass _autoSizer = new AutoSizeFormClass();

private void Form1_Load(object sender, EventArgs e)
{
    _autoSizer.controllInitializeSize(this);
}

private void Form1_SizeChanged(object sender, EventArgs e)
{
    _autoSizer.controlAutoSize(this);
}
```

## 接入方式

1. 安装 NuGet 包 `Simplerjiang.WinFormAutoSize`
2. 在窗体加载时记录初始布局
3. 在 `SizeChanged` 事件中执行自动缩放

## 适合的项目类型

- 传统 WinForms 业务系统
- 历史桌面项目维护
- 需要快速补齐自适应能力的内部工具
- 不想大改界面但希望改善缩放体验的项目

## 说明

当前类名和方法名沿用了项目早期版本的命名方式，以保证已有项目接入时的兼容性：

- `AutoSizeFormClass`
- `controllInitializeSize(...)`
- `controlAutoSize(...)`

## Related

原始仓库：<https://github.com/simplerjiang/AutoSizeFormClass>

## Source

核心实现文件：`Simplerjiang.WinFormAutoSize/AutoSizeFormClass.cs`