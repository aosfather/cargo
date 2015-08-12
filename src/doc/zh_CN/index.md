% Cargo, Rust语言的包依赖管理器

# 安装

最简单获取Cargo的方法是，获取当前稳定版本的Rust。使用 ‘rustup’ 脚本：

```shell
$ curl -sSf https://static.rust-lang.org/rustup.sh | sh
```

这将会获取当前符合你的操作系统的稳定版本的Rust，其中包含最新版本Cargo。

如果你用的是windows，你可以直接下载最新的32位([Rust](https://static.rust-lang.org/dist/rust-1.0.0-i686-pc-windows-gnu.msi)
和 [Cargo](https://static.rust-lang.org/cargo-dist/cargo-nightly-i686-pc-windows-gnu.tar.gz)) 或 64位 ([Rust](https://static.rust-lang.org/dist/rust-1.0.0-x86_64-pc-windows-gnu.msi) 和 [Cargo](https://static.rust-lang.org/cargo-dist/cargo-nightly-x86_64-pc-windows-gnu.tar.gz)) Rust 稳定版 或 Cargo 的日构建版.

或者,你可以通过源码构建Cargo。

# 让我们开始吧

使用Cargo创建一个新的工程。用命令 `cargo new`:

```shell
$ cargo new hello_world --bin
```

我们传递参数 `--bin` 来构建一个二进制程序。如果我们要构建一个库就不用传递该参数。

让我们看看Cargo为我们生成了些什么:

```shell 
$ cd hello_world
$ tree .
.
├── Cargo.toml
└── src
    └── main.rs

1 directory, 2 files
```

这就是我们所有要做得事情.首先让我们看一下文件`Cargo.toml`:

```toml
[package]
name = "hello_world"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
```

这个被成为**清单文件**它包含了Cargo编译你的工程所有需要的信息。

这是 `src/main.rs`文件内容:

```
fn main() {
    println!("Hello, world!");
}
```

Cargo 为我们生成了一个'hello world'。 然后编译它:

<pre><code class="language-shell">$ cargo build
<span style="font-weight: bold"
class="s1">   Compiling</span> hello_world v0.1.0 (file:///path/to/project/hello_world)</code></pre>

然后运行:

```shell
$ ./target/debug/hello_world
Hello, world!
```

我们也可以通过使用`cargo run` 命令去编译并运行代码:

<pre><code class="language-shell">$ cargo run
<span style="font-weight: bold"
class="s1">     Fresh</span> hello_world v0.1.0 (file:///path/to/project/hello_world)
<span style="font-weight: bold"
class="s1">   Running</span> `target/hello_world`
Hello, world!</code></pre>

# 进阶

要了解更多使用Cargo的信息，请参见[Cargo 指南](guide.html)
