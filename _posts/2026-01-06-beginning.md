# 我的C++学习之旅

---
title: "我的C++学习之旅开始啦！"
date: 2026-01-06

layout: post

---

## 为什么要开始这个计划？

作为一名游戏服务器开发者，我主要使用C++，最近需要临时转到Go。为了不荒废C++技能，我决定：

1. 建立个人博客，记录学习过程
2. 开发一个开源项目，实践C++
3. 每天进步一点点

## 01-06进展

今天成功搭建了GitHub Pages博客！

### **账号与环境准备**

**具体操作步骤：**

1. **注册GitHub账号**

   - 打开 [https://github.com](https://github.com/)
   - 点击右上角"Sign up"
   - 按提示注册，用户名建议：姓名拼音或技术相关名
   - 验证邮箱

2. **安装Git**

   ```reStructuredText
   # Windows：下载 https://git-scm.com/download/win
   # Mac：打开终端，输入 git（会自动提示安装）
   # Linux：sudo apt install git 或 sudo yum install git
   ```

3. **配置Git**

   ```bash
   # 打开终端或Git Bash
   git config --global user.name "你的名字"
   git config --global user.email "你的邮箱"
   git config --global core.editor "code --wait"  # 如果用VSCode
   ```

   

**完成标志**：能在终端运行`git --version`看到版本信息

### **创建博客（最简单方法）**

**使用最简方法：GitHub Pages + Markdown**

1. **创建博客仓库**

   - 登录GitHub
   - 点击右上角"+" → "New repository"
   - 仓库名格式：`用户名.github.io`（必须！）
   - 选择"Public"，勾选"Add a README file"
   - 点击"Create repository"

2. **克隆到本地**

   ```bash
   cd ~/Desktop  # 或你喜欢的目录
   git clone https://github.com/你的用户名/你的用户名.github.io.git
   cd 你的用户名.github.io
   ```

3. **创建第一篇文章**

   ```bash
   # 创建_posts文件夹
   mkdir _posts
   
   # 创建第一篇博客
   echo "# 我的C++学习之旅" > _posts/2026-01-06-beginning.md
   ```

4. **编辑博客内容**
   打开刚才创建的markdown文件，粘贴以下内容：

   ```markdown
   ---
   title: "我的C++学习之旅开始啦！"
   date: 2026-01-06
   layout: post
   ---
   
   ## 为什么要开始这个计划？
   
   作为一名游戏服务器开发者，我主要使用C++，最近需要临时转到Go。为了不荒废C++技能，我决定：
   
   1. 建立个人博客，记录学习过程
   2. 开发一个开源项目，实践C++
   3. 每天进步一点点
   
   ## 今日进展
   
   今天成功搭建了GitHub Pages博客！
   
   ## 明日计划
   
   1. 写一篇C++智能指针的复习笔记
   2. 设计开源项目的整体架构
   
   ---
   *每天进步一点点，就是最大的成功*
   ```

5. **推送到GitHub**

   ```bash
   git add .
   git commit -m "添加第一篇博客"
   git push origin main
   ```

6. **创建个人访问令牌（首次执行git push时密码验证失败时需要）**

   报错信息：

   ```bash
   remote: Invalid username or token. Password authentication is not supported for Git operations.
   fatal: Authentication failed for 'https://github.com/ylj-dev/ylj_dev.github.io.git/'
   ```

   解决步骤：

   - 在 GitHub 网站的 “Settings” 中，找到并进入 **“Developer settings”**。
   - 点击 **“Personal access tokens”** -> **“Tokens (classic)”**。
   - 点击 **“Generate new token”** -> **“Generate new token (classic)”**。
   - 填写一个便于记忆的 **Note**（例如 “My MacBook”），选择 **Expiration**（过期时间，如 90 天），然后勾选 **`repo`** 权限（这是推送代码所需的最小权限）。
   - 滚动到页面底部，点击 **“Generate token”**。
   - **最关键的一步**：生成后，**立即复制**屏幕上显示的令牌字符串。它像这样：`ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx`。关闭页面后将无法再次查看。
   - 回到你的终端，再次运行 `git push origin main`。
   - 当提示输入用户名时，**粘贴你第一步找到的真实用户名**。
   - 当提示输入密码时，**不要输入你的GitHub账户密码，而是粘贴你第二步生成的令牌**。
   - 成功后，系统通常会询问你是否将凭证保存到钥匙串，选择“是”以便未来无需重复输入。

7. **永久忽略`.DS_Store文件`（macOS系统文件，`git status`时看到了再进行处理即可）**

   - 详细解释

   |    项目    | 说明                                                   |
   | :--------: | :----------------------------------------------------- |
   | **文件名** | `.DS_Store`                                            |
   |  **作用**  | 保存其**所在文件夹的自定义视图设置**（非文件夹内容）。 |
   | **生成者** | macOS 系统的 **Finder**（访达）应用。                  |
   |  **位置**  | 出现在你打开过的**几乎所有文件夹**中。                 |

   - `git status`显示`.DS_Store文件`的原因

     可能通过 **Finder** 浏览过包含你博客项目的父文件夹，系统因此自动生成了这个文件。因为 `.DS_Store` 文件**通常与项目代码无关**，并且包含个人系统偏好，所以**强烈建议不要将其提交到 Git 仓库**。

   - 处理方式 --> **永久全局忽略**

     在你的电脑上全局配置 Git，忽略所有 `.DS_Store` 文件，一劳永逸：

     ```bash
     # 创建全局忽略配置文件
     echo ".DS_Store" >> ~/.gitignore_global
     # 让 Git 使用这个全局配置文件
     git config --global core.excludesfile ~/.gitignore_global
     ```

   此时，再次执行`git status`时就不会再看到`.DS_Store文件`了。

   

**完成标志**：打开 `https://你的用户名.github.io` 能看到页面

## 01-07进展

1. 写一篇C++智能指针的复习笔记
2. 设计开源项目的整体架构

---
*每天进步一点点，就是最大的成功*
