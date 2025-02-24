### 使用javac再本地终端运行乱码

![image-20250217110535029](JavaStudyQuestion.assest/image-20250217110535029.png)

这个问题的根本原因是 **文件编码不匹配**。Java文件可能是以 **UTF-8** 编码保存的，但 `javac` 编译器默认使用的是 **GBK** 编码，导致无法正确解析文件中的中文字符。

**解决方法1：**

在cmd编译的时候指定文件编码类型为UTF-8即可

```
javac -encoding UTF-8 test2.java
```



**解决方法2：**

打开代码编辑器（如 Notepad++、VS Code 等）

将文件编码改为 **GBK**：

- 在 Notepad++ 中：点击菜单栏的“编码” -> “转为 ANSI”（ANSI 在中文 Windows 下就是 GBK）。
- 在 VS Code 中：点击右下角的编码（如 UTF-8），选择“通过编码保存”，然后选择 **GBK**。

![image-20250217111754702](JavaStudyQuestion/image-20250217111754702.png)

