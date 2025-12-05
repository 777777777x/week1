# Week1 实验报告：Ubuntu系统配置与开发环境搭建
**姓名：** 李想
**学号：** 2024020133
**小组：** 第5组

## 1. 实验任务概览

本周需完成以下四个核心任务：

- [x] **任务1：安装Ubuntu与Windows双系统**
    - 目标：实现双系统引导，掌握Linux基础环境。
- [x] **任务2：安装与配置VSCode**
    - 目标：搭建C++开发环境，运行Hello World程序。
- [x] **任务3：学习Git并提交作业**
    - 目标：掌握Git基础命令，将作业提交至个人及小组GitHub仓库。
- [x] **任务4：编写Markdown实验报告**
    - 目标：使用Markdown撰写格式规范的实验报告。

## 2. 实现过程与详细步骤

### 2.1 任务1：Ubuntu双系统安装

**主要步骤：**
1.  **准备阶段**：从官网下载Ubuntu 22.04 LTS镜像文件 在官网下载VMware Fusion虚拟机
2.  **安装过程**：将磁盘上传到VMware Fusion 选择“Install Ubuntu” 
3.  **安装后配置**：设置用户名、密码，并安装系统更新。

**关键截图：**
![alt text](ubuntu桌面截图.png)

### 2.2 任务2：VSCode安装与C++环境配置

**安装命令：**
```bash
# 通过官方APT仓库安装VSCode
sudo apt update
sudo apt install code -y
```
**配置与测试：**
1.  在VSCode扩展商店安装 **“C/C++”** (Microsoft官方扩展) 和 **“Chinese (Simplified) Language Pack”**。
2.  创建测试文件 `hello.cpp`，编写第一个程序：
   ``cpp
    #include <iostream>

int main() {
    std::cout << "Hello,World!" <<
std::endl;
    return 0;
}
3.  在终端编译并运行：
   g++ "hello world.cpp" -o hello&&./hello
   **运行结果：**
   “Hello World”
   **环境截图：**
   ![alt text](<c++“Hello World”运行截图.png>)
   ![alt text](c++截图.png)
### 2.3 任务3：Git学习与作业提交

**个人仓库操作流程：**
```bash
# 1. 本地仓库初始化与配置
cd ~/Desktop/internship/week1
git init
git config --global user.name "777777777x"
git config --global user.email "2965948971@qqcom"
# 2. 连接远程个人仓库并提交
git remote add origin https://github.com/777777777x/week1.git
git add .
git commit -m "feat: 提交Week1实验报告初稿"
git branch -M main
git push -u origin main
```
**提交到小组仓库**
根据文件中的小组链接提交

## 3. 遇到的问题、分析与解决方案

| 问题描述 | 原因分析 | 解决过程与方案 | 学习点 |
| :--- | :--- | :--- | :--- |
| 系统级中文输入法失效 | `~/.profile`中环境变量`GTK_IM_MODULE`等错误指向了`fcttx`。 | 1. 通过`nano ~/.profile`编辑文件。<br>2. 将值修正为`ibus`。<br>3. **注销并重新登录**使配置生效。 | Linux环境变量的作用机制与生效方式。 |
| Git推送至GitHub时认证失败 | GitHub已禁用密码认证，需使用Token。 | 1. 在GitHub设置中生成`Personal Access Token`。<br>2. 将Token作为密码输入命令行。 | 现代Git协作的安全认证方式。 |

## 4. 实验总结与心得

### 4.1 核心知识点总结
1.  **Linux系统管理**：掌握了虚拟机安装等核心操作。
2.  **开发环境搭建**：完成了从编辑器安装、插件配置到编译运行的完整C++环境搭建流程。
3.  **版本控制**：实践了Git的本地仓库管理、远程仓库关联及多远程仓库推送的完整工作流。
4.  **文档编写**：学会了使用Markdown编写结构清晰、图文并茂的技术文档。

### 4.2 心得体会
本次实验让我从一个全新的视角接触了计算机系统。最大的收获是理解了 **“环境”** 的重要性——一个配置正确的开发环境是高效学习和工作的基石。过程中遇到最多的困难都来源于对Linux系统机制的不熟悉（如环境变量、文件权限），而每一个问题的解决都加深了对系统运作原理的理解。我也初步体会到了版本控制和规范文档在工程实践中的必要性。
