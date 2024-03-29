# ssh配置和克隆仓库

- Git 支持两种不同的协议用于与远程仓库进行通信：HTTPS 和 SSH。它们之间有一些区别：

  - **HTTPS 协议**：
    - 使用 HTTPS 协议，你可以通过 URL（比如 `https://github.com/username/repo.git`）来访问远程仓库。
    - HTTPS 协议通常需要输入用户名和密码或者访问令牌（access token）来进行身份验证。
    - HTTPS 通常在防火墙后更容易使用，因为它使用标准的 HTTP 端口（443）进行通信。
  - **SSH 协议**：
    - 使用 SSH 协议，你可以通过 SSH 密钥来访问远程仓库，而不需要输入密码。
    - SSH 协议通常比 HTTPS 更安全，因为它使用了加密的密钥来进行身份验证。
    - 使用 SSH 协议时，你需要在本地计算机上生成 SSH 密钥对，并将公钥添加到你的远程仓库提供商的账户设置中。

- 配置ssh密钥

  - cd 进入根目录

  - cd .ssh (如果no such file 直接下一步)

  - ssh-keygen -t rsa -b 4096

    - 这条命令会生成一个 RSA 类型的 SSH 密钥对，密钥长度为 4096 位。RSA 是一种常用的加密算法，4096 位的密钥长度提供了较高的安全性。

      执行该命令后，你会被提示选择密钥对的保存路径和名称，你可以接受默认路径（通常是 `~/.ssh/id_rsa`）也可以选择自定义路径和名称。然后你可以选择是否设置密码来保护私钥。

      一旦生成了密钥对，你会在指定的路径下找到私钥文件（通常是 `id_rsa`）和公钥文件（通常是 `id_rsa.pub`）。公钥文件可以提供给你的远程仓库提供商，以便你能够使用 SSH 协议进行身份验证。





