### 示例站点

- **演示站点:** 您可以访问 [演示站点](https://ilovelinuxdo.tech) 以了解 OneTimeMessagePHP 的实际效果。

如果有任何问题，欢迎提出，我会尽力改正。

以下简介是AI生成，看看就行了，[这是网页版简介](https://ilovelinuxdo.tech/introduce.html)。

好的，根据您提供的代码和示例站点信息，我将改写之前的文档，使其更准确和完整。

## 阅后即焚应用 - OneTimeMessagePHP

### 一、引言

在信息时代，隐私和安全至关重要。我们常常需要分享敏感信息，如密码、银行账户或私人消息，但又不希望这些信息被他人窥视或保存。阅后即焚应用应运而生，它允许您创建只能阅读一次的消息，阅读后自动销毁，有效保护您的隐私和信息安全。

### 二、OneTimeMessagePHP 简介

OneTimeMessagePHP 是一款使用 PHP 构建的简单安全的阅后即焚消息应用。它提供了一种便捷的方式来分享敏感信息，并确保信息在被阅读后立即销毁，防止未经授权的访问。

**主要特点:**

- **易于使用:** OneTimeMessagePHP 界面简洁直观，您只需输入消息内容，并可选择设置密码增强安全性。
- **安全可靠:** OneTimeMessagePHP 采用 AES-256-CBC 加密算法和双重加密机制，对您的消息进行加密存储，确保只有拥有正确密码的人才能解密和阅读消息。
- **开源免费:** OneTimeMessagePHP 是一个开源项目，您可以免费使用、修改和分发它，以满足您的特定需求。
- **支持 Markdown 渲染:** 您可以使用 Markdown 语法编写消息，并在查看时选择渲染成格式化的文本。
- **支持 LaTeX 公式:** 在启用 Markdown 渲染时，可以使用 LaTeX 语法编写数学公式，支持行内公式和独立公式。

### 三、功能特点

- **创建阅后即焚消息:** 您可以轻松创建只能被阅读一次的消息。消息一旦被读取，就会从服务器上永久删除。
- **密码保护 (可选):** 您可以为消息设置密码，增强安全保障。只有知道密码的人才能解密和阅读消息。
- **发件人姓名和备注信息 (可选):** 您可以选择添加发件人姓名和备注信息，方便接收者了解消息的来源和目的。
- **Markdown 支持:** 支持完整的 Markdown 语法，包括：
  - 标题、列表、链接
  - 图片、表格
  - 代码块（支持语法高亮）
  - LaTeX 数学公式：
    - 行内公式：使用单个美元符号，如：`$E = mc^2$`
    - 独立公式：使用两个美元符号，如：`$$\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$$`

### 四、使用方法

1. **创建消息:**
   - 打开 OneTimeMessagePHP 应用的首页
   - 在文本框中输入您的消息内容
   - (可选) 设置密码以保护您的消息
   - (可选) 输入发件人姓名和备注信息
   - 点击 "发送" 按钮

2. **分享消息:**
   - 应用将生成一个唯一的 URL，该 URL 指向您创建的消息
   - 将此 URL 分享给您想要发送消息的人

3. **阅读消息:**
   - 当接收者访问该 URL 时，他们将能够阅读您的消息
   - 如果消息设置了密码，接收者需要输入正确的密码才能查看
   - 一旦消息被读取，它将被自动销毁，并且该 URL 将失效

### 五、部署方法

1. **使用 Git 克隆代码库:**
```bash
git clone https://github.com/yangtb2024/OneTimeMessagePHP.git
cd OneTimeMessagePHP
```

2. **配置 `.env` 文件:**
   - 复制 `.env.example` 文件并将其重命名为 `.env`
   - 使用强随机字符串替换 `ENCRYPTION_KEY` 的值
   - 设置 `MESSAGE_EXPIRY` 的值（消息最大过期时间）
   - 配置 `SITE_ICON` (站点图标) 和 `SITE_DOMAIN` (站点域名)

3. **设置 Web 服务器:**
   - 将 Web 服务器的文档根目录指向 OneTimeMessagePHP 的目录
   - 确保 `/messages` 目录对 Web 服务器具有写入权限

### 六、安全警告

- **更换密钥导致消息失效:** 更改 `ENCRYPTION_KEY` 后，之前创建的所有消息都将无法解密和读取。
- **不要将 `.env` 文件提交到代码仓库:** `.env` 文件包含敏感信息，请勿将其提交到版本控制系统中。
- **确保服务器安全:** 请确保您的 Web 服务器配置正确，并采取必要的安全措施。
- **`.env` 文件和 `/messages` 目录的可读性:** 注意保护这些文件的访问权限。

### 七、.env 文件示例

```env
# .env 文件示例
# 请将 ENCRYPTION_KEY 替换为一个强随机字符串
ENCRYPTION_KEY=your_strong_random_string

# 设置消息的最大过期时间，格式为 "天:时:分:秒"
# 例如：7:0:0:0 表示7天
MESSAGE_EXPIRY=7:0:0:0

# 设置站点图标（Favicon）的 URL
# 以下是一些示例图标及其类型：

# 1. Base64 编码的图标
# SITE_ICON=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAIAAACQd1PeAAAADElEQVQI12P4//8/AAX+Av7czFnnAAAAAElFTkSuQmCC

# 2. 远程 URL 图标
# SITE_ICON=https://example.com/favicon.ico

# 3. 服务器路径图标
# SITE_ICON=/path/to/your/favicon.ico

# 请选择一个适合您需求的图标配置项
SITE_ICON=https://example.com/favicon.ico

# 设置站点的域名，用于生成消息链接
# 例如：SITE_DOMAIN=https://yourdomain.com
SITE_DOMAIN=https://yourdomain.com
```

请根据您的实际需求修改 `.env` 文件中的内容。

### 八、示例站点

- **演示站点:** 您可以访问 [演示站点](https://ilovelinuxdo.tech) 以了解 OneTimeMessagePHP 的实际效果。

如果有任何问题，欢迎提出，我会尽力改正。

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=yangtb2024/OneTimeMessagePHP&type=Date)](https://star-history.com/#yangtb2024/OneTimeMessagePHP&Date)
