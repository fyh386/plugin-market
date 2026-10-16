# TaskBar Plus 插件市场

TaskBar Plus 的插件市场仓库。在程序的 设置 → 插件市场 中填入本仓库地址
（`fyh386/plugin-market` 或完整 URL），即可自动加载、搜索、一键安装插件。

## 目录结构

```
plugin-market/
├── market.json          ← 插件索引（必须放根目录）
├── README.md
└── plugins/
    ├── bookmarks/       ← 每个插件一个目录
    │   ├── plugin.json  ← 插件清单
    │   └── index.html   ← 单文件插件（内联 CSS/JS）
    └── vault/
        ├── plugin.json
        └── index.html
```

## market.json 字段

| 字段 | 必填 | 说明 |
|---|---|---|
| id | ✓ | 必须与插件包内 plugin.json 的 id 一致 |
| name / version / author / description | ✓ | 展示用 |
| permissions | ✓ | 数组，可选值：network shell git clipboard session fs proxy hosts net docker，无权限写 [] |
| path | ✓ | 插件目录在仓库内的相对路径（含 plugin.json + index.html） |
| size | | 字节数，仅展示 |
| screenshots | | 截图 URL 数组，只展示第一张 |
| homepage | | 主页链接 |

支持裸数组或 {"plugins": [...]} 两种顶层格式。提交后程序端「加载插件」即可生效。
