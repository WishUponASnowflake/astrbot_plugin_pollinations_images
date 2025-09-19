### 插件文档：astrbot_plugin_pollinations_images  
> 作者：qa296  
> 说明：通过 AstrBot 调用 LLM 生成英文提示词，再使用 Pollinations.ai 的 Flux 模型生成图片。

---

### 1. 功能简介
- **指令**：`/ai生图 [主题]`
- **LLM 函数调用**：`generate_image_with_theme` 工具

---

### 2. 安装与启用
1. 将插件文件夹 `astrbot_plugin_pollinations_images` 放至 `data/plugins`。
2. 确保 AstrBot 已启用「LLM 服务」：  
   `astrbot dashboard → 服务管理 → 添加/启用一个文本模型（如 OpenAI、Ollama 等）`。
3. 重启 AstrBot，日志应出现：  
   `花粉AI图片生成插件已加载。`

---

### 3. 使用示例
| 用户输入                      | Bot 返回示例                                                                 |
|-----------------------------|------------------------------------------------------------------------------|
| `/ai生图 一只猫在太空漫步`     | *[图片]*  |
| `生成个图片，一个月饼`     | *[图片]*  |
---

### 4. 常见问题 FAQ

| 问题描述 | 排查与解决 |
|---|---|
| **Bot 回复「未配置或启用任何大语言模型服务」** | 进入 `astrbot dashboard → 服务管理`，检查是否至少启用了一个文本 LLM 服务。 |
| **Bot 回复「生成失败，请稍后再试」** | 查看 AstrBot 日志，确认 LLM 是否正常返回内容；模型可能暂时不可用。 |
| **返回图片加载失败 / 无法显示** | 极大概率是网络原因或 Pollinations.ai 服务波动：<br>1. 手动访问链接 `https://image.pollinations.ai/prompt/...` 是否正常；<br>2. 若链接 404 或超时，请稍后再试；<br>3. 若链接正常但机器人无法解析，请检查服务器网络能否直连 `pollinations.ai`。 |
| **能否自定义模型或参数？** | 当前版本固定使用 `flux` 模型、`nologo=true`；后续版本计划开放配置。 |

---

### 5. 卸载
删除插件文件夹或停用插件，日志将出现：  
`花粉AI图片生成插件已卸载。`

---

### 6. 关于 Pollinations.ai
- 官方文档：https://pollinations.ai  
- 免费、无需登录。

---

### 7. 更新日志
- 1.1.0  新增 LLM 函数调用支持，可通过 `generate_image_with_theme` 工具直接调用生成图片。
- 1.0.0  初版发布，支持 `/ai生图` 指令。
