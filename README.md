# 苏州大学实验报告模板 (LaTeX)

## 说明
本项目并非由苏州大学或其教务处发布，发布的目的是方便苏州大学的学生进行实验报告排版。若模板有问题，请在 Codeberg 仓库报告，苏州大学及其教务处没有义务修复或维护。

本模板旨在为苏州大学学生提供实验报告排版的便利工具，不完全符合苏州大学的官方格式要求。使用本模板前，请务必确认您的课程或院系是否有特定的实验报告格式要求。

授权许可及版权声明见 LICENSE。请合理使用本项目。苏州大学名称、徽标等标识归苏州大学所有，本模板中的使用仅为指示目的。

## 使用说明
本仓库包含 LaTeX 版本的实验报告模板 (`main.tex`)。

### 编译环境
- 编译器：`xelatex`
- 发行版：TeX Live / MiKTeX / MacTeX

### 快速开始
1. 确保已安装 TeX 发行版。
2. 打开 `main.tex` 文件。
3. 在文件头部的“变量定义”区域修改个人信息（姓名、学号、课程名称等）。
4. 在 `reportbox` 环境中编写实验报告正文。
5. 运行 `xelatex main.tex` 生成 PDF。

### 进阶功能说明

#### 1. 插入代码
模板内置了 `listings` 宏包用于代码高亮。在 `main.tex` 末尾已包含“附录：源代码”示例。
使用方法：
```latex
\begin{lstlisting}[language=C++]
// 你的代码
int main() {
    return 0;
}
\end{lstlisting}
```

#### 2. 插入图片
**重要提示**：由于正文包含在跨页边框 (`reportbox`) 中，**严禁使用 `figure` 浮动环境**，否则会报错（如 `Not in outer par mode`）。
请使用非浮动方式插入图片（模板中已预置注释代码）：
```latex
\begin{center}
    \includegraphics[width=0.8\textwidth]{your-image.png}
    \captionof{figure}{图片标题} % 需要 caption 宏包支持
\end{center}
```

### 字体配置
模板默认使用 Windows 系统字体（宋体、黑体、楷体）。
- **Windows**: 直接使用即可。
- **macOS / Linux**: 请确保安装了对应的字体，或在 `main.tex` 中修改 `\setCJKmainfont` 等配置为系统现有字体（如 Fandol 系列或 Noto CJK 系列）。
