![screenshot.png](docs%2Fassets%2Fimage%2Fscreenshot.png)
# AiEditor

关于 AiEditor

> AiEditor 是一个面向 AI 的下一代富文本编辑器，她基于 Web Component，因此支持 Layui、Vue、React、Angular 等几乎任何前端框架。她适配了 PC Web 端和手机端，并提供了 亮色 和 暗色 两个主题。除此之外，她还提供了灵活的配置，开发者可以方便的使用其开发任何文字编辑的应用。



## 在线演示

http://aieditor.jpress.cn


## 已完善

- [x] 基础：标题、正文、字体、字号、加粗、斜体、下划线、删除线、链接、行内代码、上标、下标、分割线、引用、打印
- [x] 增强：撤回、重做、格式刷、橡皮擦、待办事项、字体颜色、背景颜色、Emoji 表情、对齐方式、行高、有（无）序列表、段落缩进、强制换行
- [x] 附件：支持图片、视频、文件功能，支持选择上传、粘贴上传、拖拽上传、支持拖动调整大小...
- [x] 代码：行内代码、代码块、代码语言选择
- [x] 表格：左增右增、左减右减、上增下增、上减下减、合并单元格、解除合并
- [x] A I：AI 续写、AI 优化、AI 校对、AI 翻译、自定义 AI 菜单及其 Prompts
- [x] 更多：亮色主题、暗色主题、手机版适配、全屏编辑、@某某某（提及）...


## 待完善（计划中...）

- [ ] 国际化
- [ ] 团队协作
- [ ] 自动化测试
- [ ] AI 插入图片
- [ ] AI 图生图（AI 图片优化）
- [ ] AI 一键排版
- [ ] 进一步强化增贴功能
- [ ] 上传视频自动获取缩略图
- [ ] WORD 导入、导出
- [ ] PDF 导出、PDF 预览
- [ ] 类腾讯文档 UI 风格
- [ ] 类 Notion 拖拽功能
- [ ] 更多的大模型对接：文心一言、ChatGPT

## 快速开始

安装：

```shell
npm i aieditor
```

使用：

```typescript
new AiEditor({
    element: "#aiEditor",
    placeholder: "点击输入内容...",
    content: 'AiEditor 是一个面向 AI 的开源富文本编辑器。 ',
    ai: {
        model: {
            xinghuo: {
                appId: "***",
                apiKey: "***",
                apiSecret: "***",
            }
        }
    }
})
```

传统方式使用，参考 layui 示例：

https://gitee.com/aieditor-team/aieditor/tree/main/demos/layui

## 构建&运行

**构建**

```shell
git clone https://gitee.com/aieditor-team/aieditor.git

cd aieditor

# 安装依赖
npm install
```

**运行**

修改 `src/main.ts` 下的内容为：

```typescript
new AiEditor({
    element: "#aiEditor",
    placeholder: "点击输入内容...",
    content: 'AiEditor 是一个面向 AI 的开源富文本编辑器。',
    ai: {
        model: {
            xinghuo: {
                appId: "***",
                apiKey: "***",
                apiSecret: "***",
            }
        }
    }
})
```

或者直接移除 AI 的配置，如下所示（移除后，则不能使用 AI 功能）：

```typescript
new AiEditor({
    element: "#aiEditor",
    placeholder: "点击输入内容...",
    content: 'AiEditor 是一个面向 AI 的开源富文本编辑器。',
})
```

然后再命令行下执行：

```shell
npm run dev
```



## AI 功能配置

- 1、去科大讯飞注册账号 https://xinghuo.xfyun.cn
- 2、在科大讯飞服务管理中（https://console.xfyun.cn/services/bm2 ） 获取 appId、apiKey、apiSecret。
- 3、在配置中添加科大讯飞星火大模型配置

```javascript
new AiEditor({
    element: "#aiEditor",
    placeholder: "点击输入内容...",
    content: 'AiEditor 是一个面向 AI 的开源富文本编辑器。',
    ai: {
        model: {
            xinghuo: {
                appId: "***",
                apiKey: "***",
                apiSecret: "***",
            }
        }
    }
})
```