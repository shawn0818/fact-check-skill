# fact-check — 事实核查 Skill

把《事实核查手册》（中国事实核查平台「有据」主编，506 页）的方法论，压缩成一个 Agent 可直接执行的核查技能。不是资料摘要，是**动作流程**：什么情况查什么、先做什么后做什么、什么不能做。

An executable Agent Skill for fact-checking: claim triage → source tracing → evidence gathering → cross-verification → verdict & report. Covers Chinese social platforms (WeChat / Weibo / Douyin / Zhihu / Bilibili) and international news, with dedicated workflows for images, video, geolocation and chronolocation.

## 核心流程

| 步骤 | 做的事 |
|---|---|
| 1. 判断可核查性 | 能不能查 / 值不值得查 / 查了有没有风险。观点、预测、内幕来源不核查 |
| 2. 厘清核查点 | 把说法重塑成**具体问题**并拆成可独立验证的子命题（最容易做错的一步） |
| 3. 溯源 | 反搜取最早版本 → 确定原始时间地点；存档；记录传播量级 |
| 4. 取证 | 信源 6 级优先级；搜索引擎运算符；回原始语言核对译文 |
| 5. 交叉验证 | ≥2 个独立信源；**同一稿源的多家转载只算 1 个**；关键信源在付费墙后时按 L0–L4 分级取证 |
| 6. 判定与报告 | 有据 7 档标签（逐点判定 + 总判标签栏、时序类说法附时间线图）+ 6 段报告结构 |

内置 9 条铁律，其中最关键的两条：**「搜不到」≠「是假的」**（写「无法证实」，不写「X 没有发生」）；**反搜到同图 ≠ 图未被篡改**。

## 覆盖面

- **8 类虚假信息 → 首选动作**：编造式 / 错误背景挪用 / 冒名顶替 / 误导性内容 / 篡改信息 / 错误引用 / 讽刺戏仿被当真 / 阴谋论
- **图片**：Google Images / Yandex / Bing / TinEye 四件套分工，裁剪与翻转重搜，Exif，图片法医（FotoForensics），AI 生成图破绽清单
- **视频**：截帧 → 反搜 → 比对；InVID 功能；10 类虚假视频（含游戏画面、飞行模拟、Deepfake）识别特征
- **地理定位**：地形植被建筑判国别 → 街景比对 → 太阳阴影法（SunCalc）
- **时间定位**：各平台时间标记陷阱、网络时光机、航班（Flightradar24 / Plane Finder）与船舶（MarineTraffic）追踪
- **判定标签对照**：有据 7 档 / PolitiFact / 华盛顿邮报 / Snopes / 台湾事实查核中心 / Meta / Health Feedback
- **职业准则**：IFCN 与 EFCSN 准则勾选清单、法新社风格手册要点

## 安装

用户级（对所有项目生效）：

```bash
git clone https://github.com/shawn0818/fact-check-skill.git ~/.workbuddy/skills/fact-check
```

Windows：`%USERPROFILE%\.workbuddy\skills\fact-check`

项目级（仅当前项目）：

```bash
git clone https://github.com/shawn0818/fact-check-skill.git <项目目录>/.workbuddy/skills/fact-check
```

克隆后目录里必须直接有 `SKILL.md`，即本仓库根目录就是技能根目录。

## 用法

```
核查一下这条说法：<粘贴原文>
核查这张图片是不是旧图挪用：<图片>
核查这段视频，只做地理定位和时间定位：<链接>
用 fact-check 核查 X，输出有据 7 档格式的报告
```

## 仓库结构

```
.
├── SKILL.md                          # 主流程：铁律 / 六步 / 类型→动作表 / 媒介速查 / 判定 / 报告结构
├── references/
│   ├── tools.md                      # 搜索运算符速查 + 工具网址总表（反搜、地图、存档、航班船舶、数据库、AI 检测）
│   ├── sources.md                    # 信源分级、各类信源陷阱、NewsGuard / The Factual / AllSides 评级工具
│   ├── typology-and-tactics.md       # 8 类虚假信息定义与案例、AI 图破绽、Deepfake 8 项检查、地理定位推理链
│   ├── verdicts.md                   # 各机构评级体系对照表
│   ├── paywalled-sources.md          # 付费墙信源取证流程卡（L0–L4 分级、转载漂移清单、判定规则）
│   └── standards.md                  # IFCN / EFCSN 准则勾选清单、法新社风格手册要点
├── assets/
│   └── report-template.md            # 报告模板（判定标签栏 + 时间线 + 证据表）+ 写作检查表
├── LICENSE                           # CC BY-NC-SA 4.0 官方许可全文
├── NOTICE.md                         # 署名要求与许可要点说明
└── README.md
```

## 设计取舍

- `SKILL.md` 只放**决策与动作**，工具清单、案例、准则全部下沉到 `references/`，按需加载，避免把上下文一次性塞满。
- 手册最有价值的不是案例本身，而是**「类型 → 首选动作」的映射**，这部分被做成了速查表。
- 判定标签做了收敛建议：手册承认「部分虚假 / 大部分虚假」边界无法定量、读者会误读，实践中改用「误导」并写清误导点。

## 维护笔记

本技能用**真实说法跑过一遍后回改**迭代：检出一条流传说法（中俄「贝加尔力量」管道谈判）→ 按流程执行 → 记录卡壳处 → 回写进 `SKILL.md`。已因此新增的规则：

- 说法里的**推算数字**（「相差约 N 倍」）单独列为子命题，回原文核对是否有此倍数、并写明计算口径；
- 含先后顺序的说法**先拉时间线**，识别「把早已存在的状态包装成某次表态之后的新反转」；
- **付费墙信源取证**（`references/paywalled-sources.md`）；
- 判定标签从上到下逐点数齐：报告模板新增**判定标签栏**与**时间线**两节。

⚠️ 若本技能同时安装在本机（`~/.workbuddy/skills/fact-check`）与某个仓库副本，两处会分叉。改完必须先同步安装版 → 仓库副本，再 commit。

## 来源与许可

本技能由《事实核查手册》提炼而来。

- 原著：《事实核查手册》，中国事实核查平台「有据」（[chinafactcheck.com](https://chinafactcheck.com)）编制。手册为非商业性公共产品，大部分内容截至 2023 年 4 月。
- 原著许可：**知识共享 署名-非商业性使用-相同方式共享 4.0 国际（CC BY-NC-SA 4.0）**，原文见 <https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh>。
- 本技能作为原著的演绎作品，依 **CC BY-NC-SA 4.0** 发布：**不得用于商业目的**；转载、复制、节选、混编、二次创作须给出适当署名；基于本技能进行的创作也须采用同样的 CC BY-NC-SA 4.0 协议授权。
- 协议官方全文见 `LICENSE`，署名要求与许可要点说明见 `NOTICE.md`。
- 原著 PDF 未收录在本仓库中。引用案例的核查信息均取自该核查发布之时。

> 注：GitHub 的许可证自动识别不收录 CC 的「非商业性使用」类协议，因此仓库页会显示 **Other / NOASSERTION**。
> 这**不代表未声明许可**——`LICENSE` 内是 CC BY-NC-SA 4.0 的官方全文，本项目确实以该协议授权。

## 免责声明

本技能提供的是**方法论与操作流程**，不产生事实结论。核查结论依赖公开可得的证据，出现新证据时应当更新或更正。使用者需自行判断所核查内容的合规性与适用场景。
