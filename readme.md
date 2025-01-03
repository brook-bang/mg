# mg

这是一个简单的命令行工具，用于在指定文件中搜索查询字符串。此项目是根据 [此YouTube视频](https://www.youtube.com/watch?v=D_76TcfzDTU)实现的。

## 依赖

- Rust 编译器
- Cargo 构建工具

## 编译和运行

首先，确保你已经安装了 Rust 和 Cargo。你可以通过以下命令安装 Rust 和 Cargo：

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

然后，克隆这个仓库并进入项目目录：
```sh
git clone <你的仓库地址>
cd mg
```

编译项目：
```sh
cargo build
```

运行项目：
```sh
cargo run -- <查询字符串> <文件路径>
```

例如：
```sh
cargo run -- test rap.txt
```

## 项目结构
* main.rs：主程序入口，包含命令行参数解析和程序运行逻辑。
* lib.rs：包含 Config 结构体和 run 函数的实现。

## 示例
假设你有一个名为 rap.txt 的文件，内容如下：

This is a test file.
It contains some text for testing.

运行以下命令：
```sh
cargo run -- test rap.txt
```
输出:
```sh
Searching for test
In file rap.txt
With text:
This is a test file.
It contains some text for testing.
```

## 错误处理
如果命令行参数不足，程序将输出错误信息并退出：
```sh
cargo run --
```
输出：
```sh
Problem parsing arguments: not enough arguments
```