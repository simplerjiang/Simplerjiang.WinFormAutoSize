# Simplerjiang.WinFormAutoSize

Winform 自动窗体缩放类库

A Auto resize library for WinForm

原仓库：https://github.com/simplerjiang/AutoSizeFormClass


Nuget:[![Simplerjiang.WinFormAutoSize](https://img.shields.io/nuget/v/Simplerjiang.WinFormAutoSize)](https://www.nuget.org/packages/Simplerjiang.WinFormAutoSize/)
[![Simplerjiang.WinFormAutoSize](https://img.shields.io/nuget/dt/Simplerjiang.WinFormAutoSize)](https://www.nuget.org/packages/Simplerjiang.WinFormAutoSize/)


#### 环境
.net framework 4.5+

#### 使用方法：

1.Nuget 下载 **Simplerjiang.WinFormAutoSize**

2.Form中添加即可

```C#
        private Simplerjiang.WinFormAutoSize.AutoSizeFormClass asc = new Simplerjiang.WinFormAutoSize.AutoSizeFormClass();

        private void Form1_Load(object sender, EventArgs e)
        {
            asc.controllInitializeSize(this);
        }

        private void Form1_SizeChanged(object sender, EventArgs e)
        {
            asc.controlAutoSize(this);
        }
```
