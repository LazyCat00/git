# git初始化配置

- git -v

- git config --global user.name "dzl"

  `这个命令是在配置 Git，告诉 Git 在你的系统上使用全局用户名为 "dzl"。这意味着无论你在哪个 Git 仓库执行操作，Git 都会将 "dzl" 作为你的用户名。这对于提交代码和其他与 Git 相关的操作都很有用。`

- git config --global user.email 9533511@qq.com

  `这个命令会将你的全局 Git 邮箱配置为 "9533511@qq.com"。这样做可以确保在你进行提交等操作时，Git 能够将正确的邮箱地址与你的用户名相关联`

- git config --global credential.helper store

  - `这个命令将 Git 配置为使用 "store" 作为凭据助手。使用 "store" 凭据助手会将凭据（用户名和密码）存储在明文文件中，通常存储在用户主目录下的 `.git-credentials` 文件中。这样一来，在第一次向远程仓库推送代码或从远程仓库拉取代码时，你需要提供凭据，然后 Git 会将它们保存在本地，以后的操作就不再需要重复输入凭据了。`

  - 如果你在运行 `git config --global credential.helper store` 之后没有找到 `.git-credentials` 文件，可能是因为该文件还没有被创建。这是因为当你第一次使用 Git 时，如果还没有为凭据创建过文件，Git 不会自动创建 `.git-credentials` 文件。

  - 当你第一次从远程仓库拉取或推送代码时，Git 会提示你输入凭据，并在成功登录后将它们保存在 `.git-credentials` 文件中。如果你想手动创建这个文件，你可以创建一个文本文件，并将凭据信息添加到其中，然后将其保存为 `.git-credentials`。格式应该是像这样的

    ```txt
    https://username:password@github.com
    ```

    

  - 请记住，存储凭据的明文文件并不是最安全的方式，因为它们可以被其他人访问到。更安全的方式是使用其他凭据助手，比如 Git Credential Manager（Windows）、Git Credential Store（macOS）或者使用 SSH keys 进行身份验证。

- git config --global --list

  - 这个命令会列出你的全局 Git 配置信息，包括用户信息（用户名和邮箱）、凭据助手、以及其他一些可能的配置选项。你可以运行这个命令来查看当前全局 Git 配置的所有设置。

    - ```txy
      user.name=dzl
      user.email=9533511@qq.com
      credential.helper=store
      ```

