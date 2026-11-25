# 黑刃 · DSH 渗透/爬虫/破解插件索引

DSH 插件市场（format 1）索引源，收录渗透测试、红队攻防、逆向工程、安卓脱壳、爬虫采集、代码审计与模糊测试类插件。

## 用法

DSH 侧边栏 → 插件 → 发现（Discover）→ 索引源 → 添加，粘贴：

```
https://cdn.jsdelivr.net/gh/scaryburial/dsh-sec-index@main/index.json
```

（raw.githubusercontent.com 在国内主机上常超时，用的 jsDelivr CDN；备用：
`https://raw.githubusercontent.com/scaryburial/dsh-sec-index/main/index.json`）

已在 `~/.dsh/profiles/desktop/cordis.patch.yml` 里固化：

```yaml
- id: plugin-market
  name: "@deepseek-ai/dsh-plugin-market"
  config:
    indexes:
      - https://cdn.jsdelivr.net/gh/scaryburial/dsh-sec-index@main/index.json
    cacheTtlMs: 600000
```

## 收录

23 个插件，8 个分类：渗透测试 / 红队攻防 / 逆向工程 / 移动端 / 爬虫采集 / 代码审计与漏洞情报 / 模糊测试 / 蓝队防御。

标签含义：

- `需自装外部引擎`：插件只做桥接，Ghidra / IDA / REA / frida / Python 等要你自己装。
- `Windows 优先`：只在 Windows 桌面环境验证过。
- `依赖 Python 环境`：需要本机 Python 与对应包。

## 说明

- npm 来源的版本与发布时间取自 registry.npmjs.org 当天实际值，安装参数为 `包名@版本`。
- Git 来源固定了 40 位 commit（`git+https://github.com/...git#<commit>`，子目录带 `&path:/xxx`），不跟分支漂移。
- 校验用 `@deepseek-ai/dsh-plugin-market-index` 的 format 1 规则逐条比对通过。

## 维护

本地生成脚本在宿主 `C:\服务器\tools\dsh-sec-index\`：

- `scan.py` 扫 awesome-dsh-plugin 全量注册表挑关键词命中
- `resolve.py` 从 npm registry / GitHub API 取真实版本、发布时间、commit
- `build_index.py` 生成索引
- `validate.py` 按 format 1 规则校验
- `push.py` 推到本仓库
