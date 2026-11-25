# 黑刃 · DSH 渗透/爬虫/破解插件索引

DSH 插件市场（format 1）索引源，收录渗透测试、红队攻防、逆向工程、安卓脱壳、爬虫采集、代码审计与模糊测试类插件。

## 用法

DSH 侧边栏 → 插件 → 发现（Discover）→ 索引源 → 添加，粘贴：

```
https://raw.githubusercontent.com/scaryburial/dsh-sec-index/main/index.json
```

或在 profile 的 `cordis.patch.yml` 里：

```yaml
- id: plugin-market
  config:
    indexes:
      - https://raw.githubusercontent.com/scaryburial/dsh-sec-index/main/index.json
```

## 收录

23 个插件，8 个分类：渗透测试 / 红队攻防 / 逆向工程 / 移动端 / 爬虫采集 / 代码审计与漏洞情报 / 模糊测试 / 蓝队防御。

标签含义：

- `需自装外部引擎`：插件只做桥接，Ghidra / IDA / REA / frida / Python 等要你自己装。
- `Windows 优先`：只在 Windows 桌面环境验证过。
- `依赖 Python 环境`：需要本机 Python 与对应包。

## 说明

- npm 来源的版本与发布时间取自 registry.npmjs.org 当天实际值，首次安装会解析到该版本。
- Git 来源的条目固定了 40 位 commit，安装时按 commit 检出，不跟分支漂移。
- 索引里 `name` 为 npm 包名（Git 条目为仓库内包名），安装参数由市场按 `source` 生成。
