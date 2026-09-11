# 工具与网址总表

来源：《事实核查手册》第6章「信息检索」、第4章「信源」、第7–10章。工具能力截至手册成稿（2023 年 4 月），具体界面与支持范围可能已变化。

## 1. 搜索引擎运算符速查（Google，Bing/Yandex 部分兼容）

| 运算符 | 语法示例 | 说明 |
|---|---|---|
| `site:` | `site:nytimes.com China balloon`、`site:customs.gov.cn 稀土出口` | 限定域名。域名不带 `http/https/www/`，符号与词之间**无空格** |
| `filetype:` | `annual report site:credit-suisse.com filetype:pdf` | 支持 pdf / ps / dwf / kml / kmz / xls / ppt / doc / rtf / swf |
| `"双引号"` | `"John Jack Lee"` | 精确匹配；可能漏掉相关表述 |
| `-` 排除 | `"NBA球星" -詹姆斯`、`Bayraktar TB2 -site:wikipedia.org` | 减号前有空格、后无空格；必须是英文减号 |
| `*` 通配 | `"黄色的面孔有红色*"` | 通配任意词 |
| `OR` / `\|` | `奥运会 2024 OR 2028` | `OR` 必须大写 |
| `..` 范围 | `"nobel prize winners" 2000..2022` | 两个数字之间两个半角句点，无空格 |
| `intitle:` | `arms export intitle:US` | 限定标题，与词之间无空格 |
| `related:` | `related:brookings.edu` | 找同类网站 |
| `inurl:` | `India inurl:Narendra Modi` | 限定 URL |
| `imagesize:` | `Taylor Swift imagesize:2000x1200` | 像素 宽x高 |
| 高级搜索 | `google.com/advanced_search`；图片 `google.com/advanced_image_search`；视频 `google.com/advanced_video_search` | 可限尺寸、语言、时长、字幕、域名类型（.edu/.org/.gov） |

**信源辨识**：结果旁三点菜单 →「关于这条结果」/「关于这个作者」，可看站点信息、是否被其他来源广泛报道。

**其他引擎**：Bing、Yahoo、Yandex、Ask.com、DuckDuckGo、百度；新 Bing（AI 驱动）`bing.com/new`。

**关键词附加词映射**

| 需求 | 加什么词 |
|---|---|
| 找辟谣 | 虚假、存疑、错误、false、fake、wrong |
| 找报告 | 报告、研究、研究报告、调查、research、report、survey + 机构名 |
| 找数据 | 统计数据、数据、数据来源、数据库、data、dataset、database、statistics、figure、census |
| 找可视化 | 可视化、图表、仪表盘、地图、交互图表、visualization、dashboard、map、chart、graph |
| 找指标 | 指数、率、index、rate |
| 找时间线 | 时间线、时间轴、timeline |
| 找政策法律 | 文件、文献、白皮书、蓝皮书、file、document、publication、fact sheet、guideline、white paper |
| 找榜单 | 排名、rank、ranking |
| 找民调 | 民调、晴雨表、poll、survey、barometer |
| 找演讲原文 | transcript |
| 找历史档案 | archive |

## 2. 反向图片搜索

| 工具 | 网址 | 优势 | 局限 |
|---|---|---|---|
| Google Images | https://images.google.com | 人物识别、共享图源头、艺术品名称；主题识别强 | 试图识别「主题」而非图像本身，主题不清时结果差 |
| Yandex | https://yandex.com/images/ | 俄/东欧/中亚最强；显示不同尺寸、可识别文字、可裁剪；常返回更大更清晰版本 | — |
| Bing Visual Search | https://www.bing.com/visualsearch | 可识别画面中多个元素并查找同时包含这些元素的图；结果可按最新/最久排序 | — |
| TinEye | https://tineye.com/ | **唯一可按时间排序**（best match / most changed / biggest image / newest / oldest）；按图像指纹比对，不依赖关键词/元数据/水印 | 只找完全匹配（含裁剪调色缩放轻微旋转），找不到「相似」图；抓不到 FB/IG；≤100px 无法建指纹 |
| 百度识图 | — | 中文场景补充 | — |

**关键用法**

- Yandex 优于 Google 的场合：画面无明确地点标记（模糊铁路照、银行排队照）；视频截图反搜；俄语区流传图（可追到 VK）。当 Google/Bing/TinEye 无结果时优先试 Yandex。
- Google：点「查找图片来源」看含此图的网页；「工具」可选按时间（过去 1 小时…自定义）筛选，用于找初次发布页；四角裁剪工具只搜局部；结果页「文字」按钮可 OCR，支持俄语/阿拉伯语/韩语并可直接翻译。
- Bing：选「具有此图像的页面」后可按「最新/最久」排序。
- TinEye：可「filter by domain/collection」限定站点；`stock` = 图库图，`collection` = 系列图；勾选 include results not available 看存档。**oldest 是 TinEye 最早发现时间，不等于图片首次上网时间。**

## 3. InVID 验证插件

安装：https://www.invid-project.eu/tools-and-services/invid-verification-plugin/ （Chrome/Firefox）

**图片 6 大功能**：图片分析（Twitter/Facebook 图的 ID、平台、创建时间、点赞转推、评论分类）、放大镜（看车牌/机号/徽章/横幅，可裁剪/翻转/锐化，底部带 Google/Lens/Yandex/TinEye/百度 反搜按钮）、元数据（jpg/tiff 的 Exif）、取证（检测 PS 篡改，需影像知识，仅参考）、OCR、CheckGif（对比原图与篡改图，生成 GIF 展示篡改）。

**视频 5 大功能**：视频分析（仅 YouTube/Facebook/Twitter，取标题、摘要、播放点赞数、时长、上传时间、频道信息、评论分类、位置）、关键帧（支持 mp4/webm/avi/mov/wmv/ogv/mpg/flv，右键一键多引擎反搜）、YouTube 缩略图（提取 4 张并多引擎反搜）、视频版权、元数据（mp4/m4v 的作者/创建日期/修改日期/文件大小）。

**其他取帧工具**：VLC（慢放截屏）https://www.videolan.org/vlc/ ；FFmpeg https://www.ffmpeg.org/ ；watchframebyframe.com

## 4. 地图与地理定位

| 工具 | 网址 | 用途 |
|---|---|---|
| Google Maps | https://www.google.com/maps | 街景比对 |
| Google Earth | https://earth.google.com/web/ | 免费，分辨率高于 Google Maps |
| Bing Maps | https://www.bing.com/maps | 无街景，但卫星轨道不同，可得不同视角 |
| Yandex Maps | https://yandex.com/maps | 俄/中亚/东欧资源丰富，有街景 |
| Satellites.pro | https://satellites.pro/ | 集成苹果地图/OSM/Google/Yandex，可切卫星/街景，显示天气气温 |
| Dual Maps v7 | https://www.mapchannels.com/DualMaps.aspx | 输经纬度，Google 地图+街景+鸟瞰同屏，免费免注册 |
| SunCalc | https://www.suncalc.org （地理）/ http://suncalc.net/ （时间） | 太阳方位角与高度角，影子法定位 |
| PimEyes | https://pimeyes.com/ | 人脸反搜（案例中用于识别官员） |

**识别库**

| 对象 | 工具 |
|---|---|
| 车牌 | LICENCE PLATES OF THE WORLD http://www.worldlicenseplates.com/ ；Plates Mania https://platesmania.com/ |
| 高速公路标志 | Brombeer https://www.brombeer.net/signs/ |
| 旗帜 | FlagID http://flagid.org/ |

## 5. 时间定位与存档

| 工具 | 网址 | 用途 |
|---|---|---|
| 互联网档案馆 | https://archive.org/ | 历史网页 |
| 网络时光机 | https://archive.org/web/ ；存档入口 https://web.archive.org/save | 备份网页、Changes 差异对比（蓝=新增，黄=删除） |
| Chrome 扩展 | Wayback Machine 扩展 | Save Page Now、Oldest/Newest、存档次数、404 是否曾有存档 |
| archive.today | https://archive.today/ | 备用存档 |
| perma.cc | https://perma.cc/ | 备用存档 |
| Internet Archive TV News | https://archive.org/details/tvnews | 搜美国电视新闻脚本（2009 年后） |

**社交平台时间标记**

| 平台 | 显示规则 | 取准方法 |
|---|---|---|
| Twitter/X | 按用户时区显示；未登录显示 PST | 悬停时间戳（不点击）显示完整时间至分秒 |
| Facebook | 同上；未登录显示 PST | 悬停显示完整时间；若修改过发布时间，时间戳处出现时钟图标，悬停看修改前时间 |
| Instagram | 只显年月日 | Chrome 右键「检查」，搜 `datetime`，得 UTC 发布时间 |
| YouTube | 以 PST 为准，只显日期 | InVID 视频分析取 UTC 发布时间，可转本地时间 |

## 6. 航班与船舶追踪

| 工具 | 网址 | 说明 |
|---|---|---|
| Flightradar24 | https://www.flightradar24.com/ | 搜航班号/航司/机场/注册号；实时位置、高度、速度、航线；可设提醒；Play 看历史航迹 |
| FlightAware | https://flightaware.com/ | ADS-B + 雷达 + 航司数据；支持中文；免费仅近 10 天 |
| Plane Finder | https://www.planefinder.net/ | 超 10 年历史数据 |
| ADS-B Exchange | https://www.adsbexchange.com/ | 非营利；可查实时与历史 |
| MarineTraffic | https://www.marinetraffic.com/ | 搜船名/MMSI，位置轨迹 |
| VesselFinder | https://www.vesselfinder.com/ | 搜船名/MMSI，可筛选视图、看航行历史 |

**局限**：ADS-B 受天气/地形影响，军机常未装或关闭设备；AIS 在关闭时无法追踪，且存在定位欺骗（航迹出现异常几何图形即是线索）。两类工具都需交叉比对，且只能证明「某时某地存在该船/机」。

## 7. 监测与选题发现

| 工具 | 网址 | 用途 |
|---|---|---|
| Trendolizer | http://get.trendolizer.com/ | Lead Stories 开发，监测跨平台链接/图/视频互动量 |
| CrowdTangle | https://www.crowdtangle.com/ | 社交平台内容监测 |
| TweetDeck | https://tweetdeck.twitter.com/ | 推特流监测 |
| Google Trends | https://trends.google.com/home | 搜索热度 |
| 知微事见 | https://ef.zhiweidata.com/ | 中文舆情 |
| 知微舆论场 | https://trends.zhiweidata.com/ | 中文舆情 |
| 即时热榜 | http://www.jsrank.cn/ | 各平台榜单 |

监测面：微信（公众号/朋友圈/微信群/视频号）、微博（热搜与话题）、今日头条、抖音、快手、百度、知乎、B 站、新闻客户端。

## 8. 事实与数据平台

| 类型 | 工具 |
|---|---|
| 工商/司法/知产 | 天眼查、企查查、启信宝 |
| 全球统计 | Our World in Data https://ourworldindata.org/ ；Statista https://www.statista.com/ |
| 域名注册 | WHOIS https://www.whois.com/whois/ （注册商可隐藏所有者，但隐藏不了注册日期） |
| 会议实录 | C-SPAN https://www.c-span.org/ |
| 学术检索 | Google Scholar https://scholar.google.com/ ；ResearchGate https://www.researchgate.net/ ；知网 https://www.cnki.net/ ；百链云 https://www.blyun.com/ |
| 学术报道手册 | MIT Knight Science Journalism Handbook http://ksjhandbook.org/ |
| 法律原文 | 法国 legifrance https://www.legifrance.gouv.fr/ ；美国法典 https://uscode.house.gov/ |
| 权威机构 | WHO、UN（均有严谨中文版）、UNESCO、OECD、世界银行、IMF、CDC、FDA、NASA |

## 9. 图片取证与 AI 检测

| 工具 | 网址 | 说明 |
|---|---|---|
| FotoForensics | https://fotoforensics.com/ | ELA（修改处/高对比边界 ELA 值高）、JPEG%（每次修改下降，可证被改）、元数据。需影像知识，仅参考 |
| VerEXIF | https://www.verexif.com/en | 读取/删除 Exif：快门、曝光补偿、光圈、测光、闪光、ISO、拍摄时间、白平衡、镜头、分辨率，部分含 GPS |
| Hugging Face AI Image Detector | https://huggingface.co/spaces/umm-maybe/AI-image-detector | 给出 AI 生成概率 |
| Hive Moderation | https://hivemoderation.com/ai-generated-content-detection | AI 生成内容检测 |
| Mayachitra GAN Detector | https://gan-detector-mayachitra.azurewebsites.net/ | GAN 检测（测试版） |
| MIT Detect Fakes | https://detectfakes.media.mit.edu/ | Deepfake 8 项人工检查 |
| C2PA | https://c2pa.org/ | 媒体来源与历史认证标准（Adobe/Arm/BBC/Intel/Microsoft/Truepic 等 52 家） |
| Adobe 内容凭证 | https://helpx.adobe.com/cn/photoshop/using/content-credentials.html | 导出图附归因 |
| Truepic | https://truepic.com/ | glass-to-glass 拍摄签名与防篡改指纹 |
| eyeWitness to Atrocities | https://www.eyewitness.global/our-work | 记录 GPS/基站/Wi-Fi 时空 + 哈希 + 受信任监管链 |

## 10. 生成式 AI 工具（识别 AI 图时参考）

Midjourney https://www.midjourney.org/ ；Stable Diffusion https://stablediffusionweb.com/ ；DALL·E 2 https://openai.com/product/dall-e-2 ；Craiyon https://www.craiyon.com ；Bing Image Creator https://www.bing.com/create ；Adobe Firefly；Nvidia 毕加索；Runway Gen-2 https://research.runwayml.com/gen2 （文本生成视频）。

**自带水印线索**：DALL·E 右下角多色条、Craiyon 小红铅笔、Bing 左下角 Bing Logo（均可被移除或裁剪）。Google 自 2023-05-10 起在 AI 生成图原始文件加标记。
