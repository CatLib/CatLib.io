---
title: 命名规范
type: guide
order: 4
---

## 命名规范

本文档描述了CatLib框架中的命名规范。我们也建议您的项目使用这份命名规范，我们会对其保持维护。

<p class="tip">如果您要为为 CatLib 发起贡献，您必须遵循这份命名规范文档。</p>

<p class="tip">如果没有明确指定`访问级别(public|private等)`则表示对所有访问级别生效。</p>

### 概述

- 代码必须使用4个空格缩进，而不要使用制表符(tab)

### 类名及函数

- 类名必须StudlyCaps（驼峰式大写）
``` csharp
public class Bootstrap
{ 
}
```

- 函数名必须为StudlyCaps（驼峰式大写）
``` csharp
public void MyFunc()
{
}
```

### 变量,常量及属性

- 类公共全局变量名必须StudlyCaps（驼峰式大写）
``` csharp
public string MyName = "hello";
internal string MyName = "hello";
```

- 类受保护的全局变量名必须camelCase（驼峰式小写）
``` csharp
protected string myName = "hello";
private string myName = "hello";
```

- 类静态变量名必须StudlyCaps（驼峰式大写）
``` csharp
public static string MyName = "hello";
internal static string MyName = "hello";
protected static string MyName = "hello";
private static string MyName = "hello";
```

- 常量必须StudlyCaps（驼峰式大写）
``` csharp
public const string MyName = "hello";
internal const string MyName = "hello";
protected const string MyName = "hello";
private const string MyName = "hello";
```

- 静态只读变量必须StudlyCaps（驼峰式大写）
``` csharp
public static readonly string MyName = "hello";
internal static readonly string MyName = "hello";
protected static readonly string MyName = "hello";
private static readonly string MyName = "hello";
```

- 函数局部变量名必须camelCase（驼峰式小写）
``` csharp
public void MyFunc(Action func)
{
    var myFunc = func;
}
```

- 类属性名必须StudlyCaps（驼峰式大写）
``` csharp
public string Name{ get; set; }
internal string Name{ get; set; }
protected string Name{ get; set; }
private string Name{ get; set; }
```

### 接口及枚举

- 接口必须IStudlyCaps（驼峰式大写）并且以I开头
``` csharp
public interface IBootstrap { }
```

- 枚举名必须为必须StudlyCaps（驼峰式大写）
``` csharp
public enum ApplicationEvents{ }
```

- 枚举元素名必须StudlyCaps（驼峰式大写）且为单数形式
``` csharp
public enum ApplicationEvents
{
    OnStart  = 1,
    OnInited = 2,
}
```

### 代码风格及注释

-{}必须换行,且内部代码顶格书写
``` csharp
if(true)
{
    var tf = true;
}
```

-使用`///`对代码进行注释
``` csharp
/// <summary>
/// 更新Uri地址
/// </summary>
public string UpdateUri = "http://catlib.io";
```

### 委托及事件

- 公共委托，事件必须StudlyCaps（驼峰式大写）
``` csharp
public Action MyAction;
internal Action MyAction;
public event Action MyAction;
internal event Action MyAction;
```

- 受保护委托，事件必须camelCase（驼峰式小写）
``` csharp
private Action myAction;
protected Action myAction;
private event Action myAction;
protected event Action myAction;
```

### 命名空间

- 代码必须在`项目名`的根命名空间中
``` csharp
namespace CatLib
{
}
```

- 组件代码必须在`项目名.组件名`的命名空间中
``` csharp
namespace CatLib.Routing
{
}
```

### 模板

- 模板必须以T开头之后为StudlyCaps（驼峰式大写）
``` csharp
public class Bootstrap<TType>{ }
```

### 文件
- 文件名必须和类名一致
- 文件必须只使用UTF-8而不使用BOM代码
- 一个文件中不能出现2个及以上的类，除非它是内部类或者类的重载