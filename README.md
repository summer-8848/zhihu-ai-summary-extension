# 知乎AI总结助手 - 浏览器扩展版

为知乎文章、问题、回答添加AI总结功能，调用 ChatGPT/OpenAI 兼容 API 进行智能总结。

## 功能特点

- 🤖 **智能总结**：一键调用 AI 对知乎内容进行深度总结
- 📝 **支持多种内容**：文章、问题、回答全面支持
- 🔄 **流式输出**：实时显示 AI 生成的总结内容
- 💼 **多账号管理**：支持配置和切换多个 API 账号
- ⚙️ **灵活配置**：自定义 API 地址、密钥和模型
- 🎨 **美观界面**：现代化的界面设计，无缝融入知乎页面

## 安装方法

### Chrome / Edge 浏览器

1. **下载扩展文件**
   - 下载或克隆本项目到本地
   - 或直接下载 `zhihu-ai-summary-extension` 文件夹

2. **加载扩展**
   - 打开浏览器，访问 `chrome://extensions/`（Chrome）或 `edge://extensions/`（Edge）
   - 开启右上角的"开发者模式"
   - 点击"加载已解压的扩展程序"
   - 选择 `zhihu-ai-summary-extension` 文件夹
   - 扩展安装完成！

## 使用说明

### 1. 配置 API

首次使用需要配置 OpenAI API：

1. 访问任意知乎页面（如 https://www.zhihu.com）
2. 点击右下角的 **⚙️ 设置按钮**
3. 在弹出的配置面板中：
   - 切换到"账号管理"标签
   - 点击"+ 添加新账号"
   - 填写以下信息：
     - **备注名称**：账号的自定义名称（可选）
     - **API接口地址**：如 `https://api.openai.com/v1/chat/completions`
     - **API Key**：你的 API 密钥
     - **模型名称**：如 `gpt-4o-mini`、`gpt-4`等
   - 点击"测试连接"确认配置正确
   - 点击"添加账号"保存

### 2. 使用 AI 总结

配置完成后，在知乎页面上：

#### 文章页面
- 在文章标题下方会出现 **"AI总结"** 按钮
- 点击按钮，AI 会自动分析文章并生成总结

#### 问题页面
- 在问题标题旁边会出现 **"AI总结"** 按钮
- 点击可获取问题的智能总结

#### 回答页面
- 每个回答的作者信息旁都会有 **"AI总结"** 按钮
- 点击可获取该回答的详细分析和总结

### 3. 高级功能

#### 多账号管理
- 在设置面板中可以添加多个 API 账号
- 点击账号卡片即可切换当前使用的账号
- 支持编辑和删除账号

#### 自动总结
- 在"基础设置"标签中
- 勾选"自动总结"选项
- 页面加载后会自动调用 AI 生成总结

## API 配置说明

### 支持的 API 提供商

本扩展支持任何兼容 OpenAI API 格式的服务：

- **OpenAI 官方**：`https://api.openai.com/v1/chat/completions`
- **Azure OpenAI**：`https://your-resource.openai.azure.com/openai/deployments/your-deployment/chat/completions?api-version=2024-02-15-preview`
- **第三方代理**：各类 OpenAI API 代理服务
- **本地部署**：如 LocalAI、Ollama（需配置兼容接口）

### 推荐模型

- **高性价比**：`gpt-4o-mini`、`gpt-3.5-turbo`
- **高质量**：`gpt-4o`、`gpt-4-turbo`
- **其他**：任何支持的模型名称

## 文件结构

```
zhihu-ai-summary-extension/
├── manifest.json          # 扩展配置文件
├── content.js             # 内容脚本（主要逻辑）
├── popup.html             # 弹出页面
├── popup.js               # 弹出页面脚本
├── icons/                 # 图标文件夹
│   ├── icon.svg          # SVG 源文件
│   ├── icon16.png        # 16x16 图标
│   ├── icon48.png        # 48x48 图标
│   ├── icon128.png       # 128x128 图标
│   └── README.md         # 图标生成说明
└── README.md             # 本文件
```

## 从油猴脚本迁移

如果你之前使用的是油猴脚本版本：

1. 浏览器扩展会自动读取油猴脚本保存的配置
2. 首次运行时会自动迁移 API 配置
3. 两个版本可以共存，但建议只使用一个

## 常见问题

### Q: 点击按钮没有反应？
A: 请检查：
- 是否已配置 API Key
- API 地址是否正确
- 网络连接是否正常
- 浏览器控制台是否有错误信息

### Q: API 调用失败？
A: 请确认：
- API Key 是否有效
- API 接口地址是否正确
- 模型名称是否正确
- 是否有足够的 API 配额

### Q: 如何更换 API 提供商？
A: 在设置面板中：
- 添加新的 API 账号
- 点击该账号卡片切换为当前账号
- 或删除旧账号

### Q: 扩展图标显示不正常？
A: 参考 `icons/README.md` 生成对应尺寸的图标文件

## 隐私说明

- 本扩展不收集任何用户数据
- API Key 仅存储在本地浏览器中
- 所有 API 调用直接发送到你配置的服务器
- 不会上传或分享任何内容到第三方

## 开发相关

### 修改和调试

1. 修改代码后，在 `chrome://extensions/` 中点击"重新加载"
2. 打开浏览器开发者工具（F12）查看控制台日志
3. 可以在 content.js 中添加 `console.log()` 进行调试

### 打包发布

如需发布到 Chrome Web Store：

1. 确保所有图标文件已生成
2. 在 `chrome://extensions/` 点击"打包扩展程序"
3. 选择 `zhihu-ai-summary-extension` 文件夹
4. 生成 .crx 文件和私钥

## 更新日志

### v1.0.0 (2024-12-22)
- 初始版本发布
- 从油猴脚本迁移到浏览器扩展
- 支持文章、问题、回答的 AI 总结
- 多账号管理功能
- 自动总结功能
- 流式输出支持

## 许可证

MIT License

## 反馈与贡献

- 问题反馈：[GitHub Issues](https://github.com/summer-8848/zhihu-ai-summary/issues)
- 功能建议：欢迎提交 Issue 或 Pull Request
- 贡献代码：Fork 本项目后提交 PR

---

**享受 AI 智能总结带来的高效阅读体验！** 🚀
