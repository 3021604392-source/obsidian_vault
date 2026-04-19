#读书笔记Skill

完整 Skill 源码 (可直接复制)
```markdown
--- name: readingnotes 
description: 将 Apple Books 标注的 Markdown 文件整理为结构化笔记，适配 Windows 环境。仅在用户明确要求对应指令时触发。
tags: [读书, 笔记整理, Apple Books, Windows] 
version: 2.0.0-windows 
author: 适配 Windows 生态 --- 
# 触发条件 (Trigger) 
当请求命中以下口令或等价语义时启用： 
1. 整理读书笔记 
2. 整理今天读书笔记 
3. 整理 Apple Books 标注 
4. 把 Apple Books 笔记做成结构化笔记 
5. Windows 版读书笔记整理 
# 输入 (Input) 
## 数据源 
- 默认路径：`D:\Obsidian\Vault\02.Sources\apple-books-highlights\` (建议非 C 盘独立目录，避免同步冲突) 
- 支持格式：Apple Books 导出的 `.md` 标注文件、PDF 批注导出文件 
- 导入方式： 
1. 手动导出：iPhone/iPad 连接 Windows 电脑，通过 iTunes/iExplorer 导出标注文件至上述目录 
2. 自动同步：使用 iCloud 同步 Windows 版「图书」App 标注，默认同步路径为 `C:\Users\你的用户名\iCloudDrive\图书\` 
## 输入要求 
- 未指定文件时：自动扫描默认目录下所有 `.md` 文件；若需处理单个文件，需提供完整 Windows 路径（如 `D:\Obsidian\Vault\02.Sources\apple-books-highlights\三体.md`） - 编码要求：强制使用 UTF-8 编码，避免中文乱码 
# 输出 (Output) 
## 存储路径 
- 输出目录：与输入文件同目录，保持 `02.Sources\apple-books-highlights\` 结构 
- 配置建议：将输出目录纳入 Obsidian 库，避免跨目录引用导致的链接失效 
## 命名规则 
- 格式：`<原文件名>.post.md`
（例：`认知觉醒.post.md`） - 冲突处理： - 默认：不覆盖原有文件，自动追加编号
（例：`认知觉醒(1).post.md`） - 强制覆盖：需用户在指令中明确指定「覆盖旧文件」 
## 增量处理 
- 标记位置：输出文件头部添加 `<!-- readingnotes:last_processed=YYYY-MM-DD HH:MM:SS -->`
- 机制：每次执行前读取标记，仅处理未处理过的新标注，避免重复工作 
# 工作流 (Workflow) 

1. **文件读取与编码修复** - 自动识别 Windows 路径格式（`\` 与 `/` 兼容） 
- 检测文件编码，非 UTF-8 文件自动转码为 UTF-8，解决中文乱码问题 

2. **标注清洗** - 修复明显断句、移除纯噪声片段（如页码重复、无意义空格） 
- 保留原文可追溯标识（页码、位置） 

3. **语义聚合** 
- 按主题合并碎片标注，避免「一条高亮=一条 post」 
- 自动识别同一主题的标注，合并为逻辑完整的段落 

4. **多帖生成** 
- 每个主题产出 1 条「标题 + Post」组合 
- 标题基于标注内容自动提炼，Post 为聚合后的完整解读 

5. **术语卡补充** 
- 识别新术语/专有名词，自动生成术语卡（术语 + 定义 + 记忆要点）
- 术语卡存储于同目录 `terminology/` 子文件夹，便于统一管理 

6. **来源溯源** 
- 每条 post 保留 `Source` 区块，包含原文 + 可跳转的 Windows 版图书路径
（例：`file:///D:/Obsidian/Vault/02.Sources/apple-books-highlights/三体.epub`） 
# 固定输出格式 (Fixed Output Format) 
每条 post 严格按以下顺序排版： 
### 标题 
### Post 
### 术语卡（可选） 
### Source
```


## 排版规则

1. 标题 / Post/Source 之间不换行，保持紧凑
2. Post 采用简洁、易懂、可直接发布的段落表达
3. Source 用纯 Markdown 列表，格式：
    - `- 原文: ... [↗](sslocal://flow/file_open?url=%E6%96%87%E4%BB%B6%E8%B7%AF%E5%BE%84&flow_extra=eyJsaW5rX3R5cGUiOiJjb2RlX2ludGVycHJldGVyIn0=)`
    - `- 整理日期: YYYY年MM月DD日`（例：2026 年 04 月 14 日）

4. 中文标点全角，英文标点半角，统一排版规范

# Obsidian 兼容性规则 (Windows 专属)

## 路径与链接

- 支持 Windows 绝对路径与相对路径混合使用，自动转换为 Obsidian 可识别的相对链接
- 避免路径中包含特殊字符（空格、中文、符号），建议使用英文命名
- 深链接格式：`[↗](sslocal://flow/file_open?url=file%3A%2F%2F%2FD%3A%2FObsidian%2FVault%2F02.Sources%2Fapple-books-highlights%2F%E4%B8%89%E4%BD%93.epub&flow_extra=eyJsaW5rX3R5cGUiOiJjb2RlX2ludGVycHJldGVyIn0=)`

## 编码与字符

- 强制所有输出文件保存为 UTF-8 编码，无 BOM
- 转义规则：
    - 原文含尖括号（如 `<$10k>`），转义为 `&lt;$10k&gt;`
    - 特殊字符（`\`、`*`、`#`）前加反斜杠转义，避免 Markdown 解析错误
- 禁止在 `Source` 区域使用 HTML 标签（`<sub>`、`<span>` 等），纯 Markdown 书写

## 同步兼容

- 适配 OneDrive/Google Drive 同步：路径自动适配同步目录（例：`D:\OneDrive\Obsidian\Vault\02.Sources\apple-books-highlights\`）
- 避免与 Obsidian Sync 同时使用同一路径，防止冲突

# 工具适配 (Windows 生态)

## 配套工具推荐

1. **标注导出工具**
    - iTunes：官方工具，连接 iOS 设备导出图书文件
    - iExplorer：可视化工具，直接提取 Apple Books 标注，支持 Windows 7/10/11

2. **编码工具**
    - Notepad++：批量转换文件编码为 UTF-8，避免乱码
    - VS Code：打开文件时自动检测编码，一键转换

3. **同步工具**
    - Git for Windows：配合 GitHub/Gitee 实现笔记跨平台同步，支持版本回溯
    - Obsidian Git 插件：Windows 端自动提交同步，无需手动操作

## 常见问题排查

1. **路径错误**
    - 检查路径是否包含中文 / 空格，建议替换为英文路径
    - 确认文件读写权限，避免 Windows Defender 拦截文件

2. **编码乱码**
    - 用 Notepad++ 打开源文件，编码改为「UTF-8」后保存
    - 导出标注时选择「UTF-8 编码」格式

3. **同步冲突**
    - 关闭 OneDrive 按需同步功能，确保文件始终本地可用
    - 使用 Git 同步时，避免多设备同时编辑同一文件

# 指令示例 (Windows 端)

1. 整理 D:\Obsidian\Vault\02.Sources\apple-books-highlights\ 认知觉醒.md 为结构化笔记
2. 整理今天 Apple Books 标注，覆盖旧文件
3. 把 D:\iCloud\ 图书 \ 下的所有笔记整理成 post

plaintext
```

## 🚀 Windows 环境部署步骤
1. **创建目录结构**
   在 Obsidian 库中新建：`02.Sources\apple-books-highlights`，用于存放原始标注文件
2. **配置导出路径**
   - 方法1（iTunes）：连接 iPhone/iPad，在「图书」选项卡勾选「同步图书」，导出至上述目录
   - 方法2（iExplorer）：安装后连接设备，直接拖拽 Apple Books 标注文件至目标目录
3. **导入 Skill 文件**
   将上述源码保存为 `SKILL.md`，放入 Obsidian 库的 `.agents\skills\readingnotes\` 目录
4. **配置 AI 工具**
   在支持 Agent Skills 的 Windows 端 AI 工具（如 Claude Code、Obsidian LLM Hub）中，刷新技能列表，启用 `readingnotes` 技能
5. **测试运行**
   输入指令「整理 Apple Books 标注」，检查输出文件是否生成在目标目录，格式是否符合要求

## ✅ 核心优化点说明
| 优化项 | 原 macOS 版本 | Windows 版本 | 解决问题 |
|--------|--------------|------------|----------|
| 路径规范 | 基于 `/` 路径 | 支持 `\` 与 `/` 双路径，适配 Windows 格式 | 避免路径识别错误，兼容不同导出工具 |
| 编码处理 | 依赖 macOS 原生编码 | 强制 UTF-8 编码，自动转义特殊字符 | 彻底解决中文乱码、Markdown 解析错误 |
| 存储建议 | 无特定路径要求 | 推荐非 C 盘独立目录，避免同步冲突 | 适配 Windows 系统盘保护机制，提升稳定性 |
| 工具适配 | 仅支持 macOS 工具 | 新增 iTunes/iExplorer/Git 适配 | 打通 Windows 端 Apple Books 标注导入全链路 |
```