# 凤凰计划测试版 Phoenix Beta（OEBYZ）v9.9

欧陆风云 5 的东罗马（拜占庭）与欧亚全时代重制 MOD 测试版，适配游戏版本 1.4.9，界面有中文和英文。测试版更新较频繁，可能会有 bug，但可以先体验最新内容。

> **v9.9 不支持旧存档：以前任何版本的存档都不能用于这一版，请新开一局。** 想继续旧档的玩家请玩正式版。`v9.9-rc1` 做过两局实机测试（1337 拜占庭局；50 年纯观察者长局 `1337→1387`，零崩溃、无卡死，结束时内存约 8.0 GB），测出 5 项严重问题和若干次要问题。这些问题已在本版修正并通过离线检查（改动文件静态检查 0 错误、140 个决议的标题与说明词条齐全、原版覆写核对无变化），**修后没有再进游戏复测**；整体按“实验性测试版”发布。

- **Steam 创意工坊：** https://steamcommunity.com/sharedfiles/filedetails/?id=3667460405
- **GitHub：** https://github.com/miscos330/OEBYZ-Phoenix

⭐ **如果你喜欢这个 MOD，欢迎给本仓库点个 Star（页面右上角的 Star 按钮）。** Star 越多，越容易被其他玩家找到，也是对我们最直接的鼓励。发现问题可以在 Issues 里反馈，请写上开局日期、出问题的事件或界面，最好附上截图或 `error.log` 里的相关几行。

## 本模组的定位

凤凰计划（OEBYZ）是以东罗马帝国为核心的大型重制 MOD。

- **从 1337 年的危局起步。** 帝国只剩君士坦丁堡、色雷斯、马其顿、色萨利和摩里亚的一部分，亚洲一侧只剩几处据点，国库空虚。你要先稳住皇权和财政，挺过 1341 年的内战，再一步步收复失地，最终光复罗马。
- **史实优先。** 开局、人物和事件按史料校正，每条改动都有来源清单。剧情尽量写成历史上真实摆在皇帝面前的抉择。
- **制度驱动。** 帝国权威、军区、豪族、元老院和附庸阶梯互相牵制。玩法的重心是怎样治理帝国，而不只是打仗扩张。
- **不只东罗马。** 全图 15 个地区的开局都做了史实校正，大元与俄罗斯均有完整可玩 500 年专线，覆盖欧亚与远洋多战区。
- **测试版。** 新内容先在测试版放出。想要稳定体验或继续旧存档，请玩正式版。

## 主要玩法系统

- **帝国柱石：** 帝国权威、民意、内帑三项读数。行政令、帝国改革、军区、附庸、宫廷官职和帝国财政都在这个面板里。帝国权威是最紧缺的资源，几乎所有 MOD 行动都要花它。
- **军区：** 按 39 个历史辖区设立，由将军统领、自行募兵。每个军区有：
  - 地位；
  - 方针（陆军、海军、民政）；
  - 财制（将军兼管、中央委派、包税、普罗尼亚授地）；
  - 工程和兵权。

  忠诚低了会预警、叛乱，将军甚至可能称帝。卡片上有朝廷每月在这个军区上的账，也可以把军区交给将军托管。
- **疆域三圈：**
  - 内圈是五种地位的行省（内地、边镇、总督区、特许城邦、宗室封邑），有元老院表决、大区总凯法勒、清丈和分封宗室；
  - 中圈是附庸阶梯：朝贡 → 罗马同盟 → 行省化附庸 → 设省；
  - 外圈是君王大家庭、帝国尊号、遣使纳币和“收复故省”宣战理由。
- **征伐与罗马再征服：** 先在“群雄逐鹿”中拿下巴尔干和安纳托利亚，再向埃及、意大利、伊比利亚等方向发动征伐。敌方会反击、求援、宣布圣战。光复满 10 个地区即完成罗马再征服，之后还有“罗马之重负”。
- **宫廷与豪族：** “琼筵序次”里有 7 个宫廷官职。豪族名册上的家族会扩张势力，可以拉拢、打压、抄家；放任不管会引发“拜占庭式的阴谋”。
- **帝国财政：** 国库与内帑分两本账；铸币、借贷、包税各有代价。加拉塔的热那亚人从开局起就截走关税。
- **历史关口：** 1341 年两约翰之战、静修派之争、杜尚的塞尔维亚、奥斯曼人渡海、1348 年加拉塔之争。

## v9.9 主要内容（整合 v9.0 / v9.5 / v9.6 / v9.7 / v9.8 罗马多神教 / v9.9 全生态）

对比 `v8.5`，事件由 **1,747 个增至 1,946 个（+199）**，决议由 **104 个增至 140 个（+36）**，中文词条由 **30,907 条增至 34,870 条（+3,963，英文同步 36,601 条）**，原生 `.dds` 美术与图标资产由 **646 枚增至 888 枚（+242，发布包未压缩增加约 150.6 MB）**，开局游戏规则扩至 **12 条**。

- **《罗马多神教（Religio Romana）》深度重制（v9.8）：** 保留原版 ID `hellenism_religion` 无损更名、不强锁 D008、修补 4 处原版多神教错字；新增 **10 尊新神 × 50 项新神谕**（通过「六柱万神殿」动态入祀轮换保持 6 尊活跃神），配齐 **103 枚专用图标与原版大理石基底合成的 10 尊新神立像**；新增 8 面向、2+1 宗教律法、罗马大祭司团 IO、6 项古典祭仪、9 座可重修古典大神殿与三阶「众神和平」加成、4 项时代 5–6 科技与 35 个四幕史诗事件（仅玩家可控转教，AI 不自发改信）。
- **军区 2.0 与三大文明经典系统精修（v9.7）：** 1337 拜占庭开局改为三选一（推荐选项 A 仅立 2 个核心大军区，大幅减轻外交容量压力），军区忠诚档自动同步原版附庸忠诚度，新增拆分/整并与 4 项驭将之术；深化拜占庭豪族/内战/双轨罗马化、大元宝钞/漕粮/投下、罗斯诺夫哥罗德/哥萨克/特辖军与五大枢纽市场需求桥接。
- **AI 2.0、殖民 2.0、四速有机同化与全球宗教（v9.9）：** 15 条 AI 扩张走廊 + 反边界癌 + 非作弊财政紧缩 + 年度 AI 总管；4 个零覆写原创欧亚殖民宪章目标与 5 生态限速；纯 C++ 地块级四速有机同化（都会/海港/低控山区/边疆）+ 5 大文化融合弧 + 七大文化首都争霸；景教/东方正统教/伊斯兰/新教改革 8 面向/腾格里 4 神/印度教 6 化身 + **24 座新圣地**。
- **政务减负、奇观修会、原生引擎与 3D 兵模（v9.0 / v9.5 / v9.6）：** 左下角 8 钮快捷栏、帝国熵增仪表盘与 5 项顶栏预警、可选政务自动化总控台（默认关闭）、28 项议会议题、4 类新附庸与 24 项交互、12 座欧亚奇观与修会、18 项文化融合科技、规则 #11（同盟降级保独开关）与 #12（动态思潮起源）、7 色决议分类、5 文明摄政与 3 条帝国大道、俄罗斯/大明/草原 18 国零覆写 3D 兵模及 160 城 LDE 批五百科。
- **工坊生态兼容与实机排雷：** 自 v9.6 起至 v9.9 新增文件零新增原版覆写与 GUI 覆写，对 28 个常见本地工坊模组保持 0 新增碰撞；首轮实机测试报出的 5 项严重问题与多项次要问题已在本版修正（修后未实机复测）。

完整改动见 [CHANGELOG.md](CHANGELOG.md)。

## v8.5 主要内容（整合 v7.0–v8.5 全时代大版本）

事件从 1372 个增加到 1747 个（+375），中文文本从约 18300 条增加到约 23800 条，新增 28 张原创高精度原生 `.dds` 美术资产（发布包增加约 59 MB）。**1337–1515 已跑过 178 年纯观察者实机长局（零崩溃、无卡死）；那一局之后的 v8.5 热修与 1560–1836 近代后期线路只过了 23/23 离线门禁，没有再进游戏复测，整体仍按“实验性测试版”发布。**

- **三大文明 500 年完整主线（1337–1836）：**东罗马近代线（33 幕）、大元近代线（1450–1750）、俄罗斯玩家可玩全线（莫斯科→第三罗马→彼得改革）；配套 **23 支跨时代特色兵种 + 20 项军事科技**。
- **五大旗舰局势与全球战区：**大元中兴、金帐分裂、拜占庭文艺复兴、东方十字路口、两帝之争（均配原生横幅与徽章）；拓展西欧反罗马同盟、南亚/东南亚海上丝路、马格里布与非洲总督区、北欧/多瑙河/东亚边缘及远洋殖民线。
- **帝国熵增引擎 & 12 强动态反霸权 AI：**新增 10 项开局游戏规则自由开关，打破中后期滚雪球无聊期，与“罗马之重负”零双重扣减合并。
- **UI 2.0 & 编年史 2.0 & 28 张原生美术：**主界面左下角的快捷导航栏、6 分页 74 线编年史 2.0、LDE 批四词库、227+ 核心事件配图升级与 4 张欧亚载入画面。
- **修正历史遗留与原版缺陷：**针对 1337 拜占庭—艾登自动保独做了修正、补了 8 条原版 `gui.log` 简中报错对应的词条、修正了 178 年长局里记到的运行时报错（都不改原版文件，修后未实机复测）；补齐 28 条原版缺漏词条（实机已见清零）。

完整改动见 [CHANGELOG.md](CHANGELOG.md)。

## v6.8 主要内容

事件从 1229 个增加到 1372 个，中文文本从约 17200 条增加到约 18300 条，另有东罗马与大元的三套新外观（发布包因此大了约 100 MB）。原定 v6.7.1 的修正也在这一版里。**新内容大多只在短测试局里用测试按钮看过一次，没有跑过长局，全部按“实验性”发布。**

- **军区与经济：**军区账本（卡片上一行朝廷本月的账，只显示）；军区托管；经营边区第四、五步（招资、年金与赎回、归化）；罗马商社第三期（坐大、收归国有、希俄斯的股份、散伙）；海军军区按船数领饷。
- **拜占庭各线：**中兴与霸业第二、三批（改定方略、塞萨洛尼基守城掷骰、四路征伐后的事件）；失城之后的教会；最后的围城第三期；1337 年开局关掉与本模组重复或冲突的几个原版事件。
- **巴尔干与拉丁世界：**塞尔维亚与多瑙河防线一至三期（1371–1444）；阿尔巴尼亚与斯坎德培一期；爱琴海诸领主一期；拉丁世界四期（教廷）、五期（立陶宛的洗礼与托伦和约）。
- **大元：**钞法、海运与京仓、大元中兴、高丽各一期；1340 年立皇太子；投下宗王与食邑；土司第三轮；六位元廷人物。哈密开局改归豳王
- **外观：**东罗马军队、大元军队的单位模型和大元官服肖像（来自竹子大王的社区DLC，经竹子大王本人同意使用）。

完整改动见 [CHANGELOG.md](CHANGELOG.md)。

## 上手建议

1. 开局的“设立军区”事件推荐选 **选项 A（精简核心大军区制：仅建色雷斯—马其顿与塞萨洛尼基两个核心军区）**，开局外交容量占用更低；后期随时可拆分或增设。
2. 在“帝国财政”里调高“维系帝国权威”的拨款，抵消权威每月的衰减。
3. 开局财政偏紧，先存钱。1341 年前预留约 250 金币和 5 帝国权威，就可以选择避免内战；趁安德洛尼卡三世在世时“加冕共治皇帝”。
4. 想体验《罗马多神教》路线的玩家，可在触发米斯特拉斯卜列东事件或 1415 年后（或同时直辖君堡、雅典、罗马）通过决议「重光罗马古教」主动转教；不想转教则正教主线完全不受影响。
5. 善用左下角 8 钮快捷导航栏与 12 项开局游戏规则（例如规则 #11 可关闭同盟自动降级保独、规则 #12 可开启动态思潮起源）；“设置”里的调试开关正常游玩不要点。

## 后续更新计划

计划会根据测试和玩家反馈调整，以实际更新为准。

- **v10.5（优先推进 · 可选传奇架空资料片）：** 《第四奥德赛 · 极乐洲新罗马（*Nova Elysia*）》——由开局规则 `#13` 自由开关（1453 流亡触发 / 1337 提前启航 / 关闭），深度联动 `v9.8` 罗马多神教（新西海万神殿）与 `v9.9` 殖民/原住民盟邦体系，支持重返地中海与“大西洋双都帝国”双结局。
- **v10.0（全欧亚可玩大主角）：** 金帐/帖木儿、马穆鲁克、波立三海联邦、威尼斯/热那亚与大明/满洲双轨 500 年主角线 + 25 国天命任务链。
- **v11.0–v12.0（终局、全球文明与底层深化）：** 动态疫病检疫港与后期霸权、波斯/印度/日朝/西欧全球扩展、帝国御用工场与跨时代特色征召/陆海军阵、欧亚世界协调会与原生 Wwise 情境音乐调度。
- **v12.5–v13.0（历史大危机与全球补完）：** 谍报密谋与海洋私掠/雇佣兵哗变、小冰期与十六世纪白银价格革命、深度议会诉求与真实叛军纲领、非洲三轴与美洲本土现代化抗衡线。

## 已知问题

- 本版整体按“实验性测试版”发布：`v9.9-rc1` 做过 1337 拜占庭局与 50 年纯观察者长局（`1337→1387`）；之后的热修只过了离线检查，修后没有再进游戏复测。
- 旧存档不支持，请新开一局；只适配 EU5 `1.4.9`。
- 下面几项是 rc1 实机里出现过的问题，本版已修正但修后未实机复测，如果仍然遇到请反馈：29 个新决议的标题和说明显示成原始键名；罗马多神教神殿面板显示 16 尊神（设计是 6 尊）且未入祀的神也能求神谕、也给加成；军区开局选项 A 的第二个军区（塞萨洛尼基）没有初始化、忠诚为 0；开局和长局的 `error.log` 报错量偏大。
- 下面这些新内容只过了离线检查，实机还没逐项看过：9 座大神殿的重修与“众神和平”加成、四速同化修正、少数族群特权、4 个新殖民宪章目标、24 座新圣地、军区拆分/整并与驭将之术、摄政与教育、帝国大道、俄罗斯/大明/草原 3D 兵模、顶栏提醒。
- 大元中兴局势：rc1 实机里 6 年进度只到 29/100，节奏可能偏慢，后续版本再调。
- 打开国际组织成员页（包括罗马大祭司团）时日志里可能刷布局提示；`YUA` 文化容量、`SSK` 封邑等早期遗留的非阻断日志提示仍在。
- 1337 开局头 20 天东正教农民减少约 6.1 万、以及大元建筑式行省偶尔加入原版独立运动，属于原版底层人口/外交结算机制，仍在持续跟踪。
- 军区（建筑型国家）不能自行招募正规军：这是原版引擎规则（与汉萨同盟相同）。
- 拜占庭部队模型在日志里有两类无害贴图/挂点提示（头盔多余 UV 通道、重步兵盾牌缺默认项），不影响游戏内显示。
- “两帝之争”局势中，6 项公开行动按拜占庭、神圣罗马帝国、奥地利、俄罗斯、教廷五方阵营分属显示，拜占庭视角看到 2 项属正常设计。
- 1430 年代奥斯曼处于苏丹国阶位时出现叠字国名，为 EU5 1.4.9 原版突厥王朝后缀规则，不影响游玩。

## 安装

- **Steam 创意工坊（推荐）：** 订阅上面的链接，然后在游戏的“模组和DLC”里把它加入播放集。
- **手动安装：**
  1. 下载 [Release](https://github.com/miscos330/OEBYZ-Phoenix/releases) 里的压缩包；
  2. 解压出 `OEBYZ-Phoenix-v9.9` 文件夹；
  3. 把整个文件夹放进 `文档\Paradox Interactive\Europa Universalis V\mod\`；
  4. 在播放集里启用。

## 兼容性

- 只适配游戏版本 1.4.9。游戏更新后，部分覆盖原版的开局文件可能需要重新生成。
- 不支持旧存档：以前任何版本的存档都不能用于这一版，请新开一局。
- MOD 改写了 1337 年开局的部分原版文件（国家、建筑、外交、国际组织、地区偏好）和几份原版事件文件（拜占庭、保加利亚、热那亚、塞尔维亚、奥斯曼的崛起等）。改同一批原版文件的模组大多不兼容，不建议同时启用。
- 界面有中文和英文。
- 其他拜占庭整体改版、改动 1337 开局或同一批地区的模组，未做兼容，不建议同时启用。

## 制作人员

- **制作：** 寐夜空灵、miscos330
- **军区辖区数据：** 来自“拜占庭重置:涅槃”（Byzantium Overhaul: Nirvana，[创意工坊 3602306286](https://steamcommunity.com/sharedfiles/filedetails/?id=3602306286)），已获授权。
- **国家、文化、王朝等的历史介绍：** 来自“描述扩展：国家、文化、王朝及更多”（Descriptions Expanded，[创意工坊 3838927963](https://steamcommunity.com/sharedfiles/filedetails/?id=3838927963)），© Descriptions Expanded contributors，按 CC BY-SA 4.0 使用。凤凰计划在其基础上为自有的国家和家族补写了条目，并让两处文本与本 MOD 的原文合并；这些增补同样按 CC BY-SA 4.0 提供。详见包内 `third_party/descriptions_expanded/`。
- **致谢：** 感谢以下创意工坊模组。竹子大王的社区DLC（创意工坊 3763953914）：大元官服肖像（四档圆领袍、蒙古交领衣、蒙古帽、展脚幞头、垂翅幞头）与元廷六位人物（欧阳玄、许有壬、苏天爵、揭傒斯、泰不华、余阙）的能力估值，东罗马军队的单位模型（罗马盔、具装覆面盔、札甲、斯帕塔剑、鸢盾与扇形盾、拉布兰旗），大元军队的单位模型（护脸盔、札甲、范阳笠、绑腿、直刀与雁翎刀、虎头盾、半具装马铠）。模型与贴图照原样借用并改名，定义与挑选规则是我们自己写的，经竹子大王本人同意使用；文件清单见包内 `third_party/bamboo_king/`。下列模组给了我们结构或写法上的借鉴，脚本和文字都是我们自己写的：《The Reich / 帝国》（3823496063）——边疆定居的登记与核实、出资人的回报与赎回、战后分封（经营边区、战后安排），换地前按名单快照、只转仍归原主之地的写法与把原版立陶宛皈依包成可调用效果的写法（拉丁世界五期），“关键一块先到手、其余才做”的步骤顺序（塞尔维亚二、三期）；《Rise of the British Empire》（3621489583）——特许公司的分步解锁、两级买地、具名租让与“收归国有 / 退出”两种结局（罗马商社）；“拜占庭重置:涅槃”（3602306286）——按类别、只记不动钱的月账（军区账本）；《Basileia Romaion: 1337》（3618199037）——把地交给已定义而不在场的国家来让它复国（黑羊、白羊、伊梅列季、突厥诸侯）；《Refined Colonization》（3816832717）——商站的准入名单（招民垦荒）；满洲-清朝风味扩展（3714561641）——藩王附属类型的结构（投下宗王），朝贡觐见“按请求裁决、按对方收入计价”的事件结构与附属出兵的意愿（高丽），军粮储备的省份修正与省份粮食的读法（海运），通胀档位的写法与每月通胀的量级（钞法）；National Destinies（国家天命，3668193813）——“先选路线、再分三阶、每阶一张条件清单”的结构（大元中兴）；Praecepta Militaria - Propyrglon tou Dunabeos（3820674880）——“保护而非附庸”的单向关系的建立与撤销（塞尔维亚二、三期）；Flavorium Universalis - Rhomania（3791634667）——“丝路重开”修正的键组合与量级（中兴与霸业第三批）；MEIOU and Taxes（3735059838）——把通胀按小数读取的写法（钞法）。天朝拓展（Celestial Empire Expansion，3810799047）、Praecepta Militaria 系列、The Persianate World 和 Rhomania - a Journey To The West 的脚本注释里记下的引擎行为，帮我们查出并避开了几处问题。

## 许可

见 [LICENSE.md](LICENSE.md)。

---

# Phoenix Beta (OEBYZ) v9.9 — English

The beta of an Eastern Roman (Byzantine) and Pan-Eurasian overhaul for Europa Universalis V, made for game version 1.4.9. The beta updates often and may contain bugs, but it has the newest content.

> **v9.9: Old saves are not supported: saves from any earlier version will not work with this one. Start a new game.** `v9.9-rc1` ran two live EU5 `1.4.9` sessions (a 1337 Byzantium game and a 50-year pure observer run `1337→1387` with no crash or freeze; about 8.0 GB of memory at the end) and turned up 5 serious and several minor problems. They are fixed in this build and passed the offline checks (static check of the changed files, title and description keys of all 140 decisions, vanilla-override check), but **the fixes were not re-checked in game**. This remains an experimental beta.

- **Steam Workshop:** https://steamcommunity.com/sharedfiles/filedetails/?id=3667460405
- **GitHub:** https://github.com/miscos330/OEBYZ-Phoenix

⭐ **If you enjoy the mod, please star this repository.** Stars help other players find it and are the most direct encouragement for us. Bug reports are welcome in Issues.

## What this mod is

- **Start from the crisis of 1337:** the empire holds only Constantinople, Thrace, Macedonia, Thessaly and part of the Morea, a few footholds in Asia, and an empty treasury. Secure the throne and the finances, survive the civil war of 1341, win back the lost lands, and in the end restore Rome.
- **History first:** the start, characters and events are checked against the sources, and stories follow the choices emperors actually faced.
- **Driven by institutions:** imperial authority, themes, great houses, the senate and the ladder of subjects pull against each other. The game is about governing, not only conquest.
- **Beyond Byzantium:** the start is corrected in 15 regions across the map, with full 500-year playable lines for Byzantium, Great Yuan, and Russia across Eurasian and overseas theatres.

## Main systems

- **Pillars of Empire:** one panel for authority, public opinion, the privy purse, decrees, reforms, themes, subjects, court and finance.
- **Themes:** 39 historical regions led by strategoi who raise their own troops, each with a status, a policy, a fiscal regime and works. Low loyalty brings revolts, and a strategos may claim the throne. Each card shows the crown's monthly account, and a theme can be handed to its strategos to manage.
- **Three rings of territory:** provinces with five statuses and a senate; a ladder of subjects from tributary to province; the Family of Kings, dignities and buying peace.
- **Imperial campaigns and the Roman Reconquest:** win the Balkans and Anatolia, then campaign towards Egypt, Italy, Iberia and beyond; restore 10 regions to complete the Reconquest.
- **Court, great houses and finance:** seven court offices, great houses to court or curb, and separate treasury and privy purse.

## Highlights of v9.9 (Consolidated v9.0–v9.9 Release)

Compared to `v8.5`, events grow from **1,747 to 1,946 (+199)**, decisions from **104 to 140 (+36)**, English localisation from **32,640 to 36,601 keys (+3,961; Chinese 34,870)**, native `.dds` art and icons from **646 to 888 (+242, +150.6 MB unpacked)**, and Game Rules from **10 to 12**.

- **Religio Romana Overhaul (v9.8):** Non-destructive rename of `hellenism_religion` with no D008 lock and 4 vanilla loc fixes; **10 new deities × 50 new omens** rotating through the 6-pillar Hexapantheon (103 icons & marble-style statues), 8 aspects, *Collegium Pontificum* IO, 6 priestly actions, 9 rebuildable Grand Temples with 3-tier *Pax Deorum* synergy, 4 Ages 5–6 advances, and 35 events across 4 Acts (human-only conversion).
- **Theme System 2.0 & Core Refinements (v9.7):** Streamlined 1337 Byzantine opening choice (recommended Option A: 2 core themes), automatic loyalty-band sync to vanilla subject loyalty, split/consolidate & 4 Arts of Managing Generals, plus deep updates for Byzantine Houses/Civil Wars, Great Yuan Chao/Grain/Tou-Xia, Russia Veche/Cossacks/Oprichnina, and 5-hub market demand bridges.
- **Eurasian AI 2.0, Colonization 2.0, 4-Speed Assimilation & Global Religion (v9.9):** 15 AI corridors, anti-bordergore, non-cheat fiscal austerity & O(1) annual AI Macro-Steward; 4 zero-override Eurasian colonial charter goals & eco-zone pacing; location-level 4-speed organic assimilation, 5 hybridization arcs & 7 Cultural Capitals race; expanded Nestorian, Miaphysite, Islamic, Protestant (8 aspects), Tengri (4 gods), Hindu (6 avatars), Shinto & Theravada content + **24 new holy sites**.
- **Automation, Wonders, 3D Units & Zero-Collision Ecosystem (v9.0 / v9.5 / v9.6):** 8-button bottom-left Quick Nav bar, Entropy Dashboard & 5 top-bar alerts, optional Governance Automation console, 28 parliament issues, 4 subject types & 24 interactions, 12 Eurasian wonders & orders, 18 culture fusion advances, Game Rules #11 & #12, 7-color decisions, 5 regencies, 3 Imperial Roads, 18-tag zero-override Russia/Ming/Steppe 3D units, and 160-city LDE Batch 5. Zero new file collisions against 28 tested local Workshop mods.

See [CHANGELOG.md](CHANGELOG.md) for the full list.

## Highlights of v8.5 (Full 1337–1836 Mega Release, v7.0–v8.5)

Events grow from 1372 to 1747 (+375), Chinese localisation keys grow from about 18300 to about 23800 (with full English coverage), and 28 bespoke native `.dds` artworks are added (+59 MB). **1337–1515 ran 178 years in a live observer game without a crash or freeze; the hotfixes made after that run and the 1560–1836 late-game lines passed only the 23/23 offline checks, were not re-checked in game, and are released as an experimental beta.**

- **500-Year Three-Civilisation Arc (1337–1836):** Byzantine Early Modern line (33 events), Great Yuan Early Modern line (1450–1750), and a full playable Russia arc (Moscow → Third Rome → Petrine reforms), backed by **23 cross-era unique units and 20 military advances**.
- **Five Flagship Situations & Global Theatres:** Yuan Restoration, Golden Horde Troubles (multi-khanate splintering), Byzantine Renaissance, Eastern Crossroads, and War of the Two Emperors — plus Western Europe Anti-Roman League, Maritime Silk Road (South/SE Asia), Maghreb/Barbary & Africa Exarchate, Nordic/Danube/East Asia rim, and Far Seas overseas ventures.
- **Empire Entropy Engine & 12-Major Anti-Hegemon AI:** Configurable via 10 Game Rules to keep late-game empires challenging without double-stacking penalties with the Burden of Rome.
- **UI 2.0, Chronicle 2.0 & 28 Native Artworks:** a Quick Nav bar at the bottom left, 6-tab 74-line Chronicle 2.0, LDE Batch 4 history tooltips, 4 Eurasian loading screens, and 227+ upgraded event illustrations.
- **Vanilla & Legacy Fixes:** a fix for the 1337 Byzantium–Aydın auto-guarantee, fixes for 8 vanilla `gui.log` Chinese errors and for the run-time errors recorded in the 178-year run (none re-checked in game yet), and 28 missing vanilla keys filled in (seen clean in game).

See [CHANGELOG.md](CHANGELOG.md) for the full list.

## Highlights of v6.8

Events grow from 1229 to 1372, and three new looks arrive for the Byzantine and Yuan armies and the Yuan court (the package is about 100 MB larger). The fixes planned for v6.7.1 are included. **Most of the new content has been triggered once in short test games with test buttons, never in a long game; all of it is experimental.**

- **Themes and the economy:** the crown's ledger on each theme card (display only); managed themes; frontier programmes, steps 4 and 5 (backers, annuities and buy-back, settlement); the Roman Company, phase 3 (its rise, nationalisation, the shares of Chios, winding up); naval themes now get their pay.
- **Byzantium:** Restoration and Hegemony, batches 2 and 3 (changing the emphasis, a defence roll for Thessalonica, events after four campaigns); the Church after the City is lost; the last siege, phase 3; a few vanilla events that clash with the mod no longer fire in the 1337 start.
- **The Balkans and the Latin world:** Serbia and the Danube line, phases 1-3 (1371-1444); Albania and Skanderbeg, phase 1; the lords of the Aegean, phase 1; the Latin world, phase 4 (the papacy) and phase 5 (the baptism of Lithuania and the Peace of Thorn).
- **The Yuan:** paper money, sea transport and the capital granaries, a Yuan restoration and Goryeo, each a first phase; a crown prince in 1340; the touxia princes and their appanages; a third round of tusi changes; six officials at the start.
- **Looks:** unit models for the Byzantine and Yuan armies and Yuan court dress, from Bamboo King's Community Flavor Pack, used with the maker's consent.

## Roadmap

Plans will change with testing and player feedback.

- **v10.5 (first in line, an optional alternate-history expansion):** *Fourth Odyssey: Nova Elysia*, switched by a Game Rule (triggered by the exile of 1453, an early departure from 1337, or off), tied to the v9.8 Religio Romana and the v9.9 colonisation and native-ally systems.
- **v10.0 (Pan-Eurasian protagonists):** 500-year lines for the Golden Horde and the Timurids, the Mamluks, Poland-Lithuania, Venice and Genoa, and a Ming/Manchu dual track.
- **v11.0–v12.0 (endgame, world civilisations and deeper systems):** plague and quarantine ports, late-game hegemony, Persia, India, Japan and Korea, Western Europe, imperial workshops and era-specific levies.
- **v12.5–v13.0 (historical crises):** espionage and plots, privateers and mercenary mutinies, the Little Ice Age and the price revolution, deeper parliaments and rebel programmes, Africa and the Americas.
- **Ongoing:** keep pace with Europa Universalis V patches and maintain the 1337 start.

## Install

- **Steam Workshop (recommended):** subscribe via the link above, then add the mod to your playset.
- **Manual:** unpack the [release](https://github.com/miscos330/OEBYZ-Phoenix/releases) archive into `Documents\Paradox Interactive\Europa Universalis V\mod\`, then enable it in your playset.

## Compatibility

- Game version 1.4.9 only.
- Old saves are not supported: saves from any earlier version will not work with this one. Start a new game.
- The mod rewrites part of the vanilla 1337 start files (countries, buildings, diplomacy, international organisations, regional preferences) and a few vanilla event files (Byzantium, Bulgaria, Genoa, Serbia, the rise of the Ottomans and others). Mods that change the same vanilla files are mostly incompatible; we advise against running them together.

## Credits

- **Made by:** 寐夜空灵, miscos330
- **Theme-region data:** from Byzantium Overhaul: Nirvana ([Workshop 3602306286](https://steamcommunity.com/sharedfiles/filedetails/?id=3602306286)), used with permission.
- **History texts for countries, cultures, dynasties and more:** from Descriptions Expanded: Countries, Cultures, Dynasties & More ([Workshop 3838927963](https://steamcommunity.com/sharedfiles/filedetails/?id=3838927963)), © the Descriptions Expanded contributors, used under CC BY-SA 4.0. Phoenix adds entries for its own countries and families and merges two texts with its own; these additions are offered under CC BY-SA 4.0 as well. See `third_party/descriptions_expanded/` in the package.
- **Thanks:** Thanks to these Workshop mods. Bamboo King's Community Flavor Pack (Workshop 3763953914): the Yuan court portraits (four grades of round-collared robe, the Mongol wrap coat and hat, two kinds of futou), the abilities estimated for six Yuan officials, and the unit models of the Byzantine and Yuan armies. Meshes and textures are used as they are under new names, the definitions and selection rules are ours, with the maker's consent; the file list is in `third_party/bamboo_king/`. These mods lent us structures or techniques, while all script and text are our own: The Reich (3823496063): registering and verifying frontier settlement, backers' returns and buy-back, post-war enfeoffment (frontier programmes, post-war settlement), taking a snapshot before land changes hands and moving only what the old owner still holds, wrapping the vanilla conversion of Lithuania as a callable effect (Latin world phase 5), and the order "the key piece first, the rest after" (Serbia phases 2-3); Rise of the British Empire (3621489583): the chartered company's staged unlocks, two-tier land purchases, named grants and its two endings (the Roman Company); Byzantium Overhaul: Nirvana (3602306286): a monthly ledger by category that records without moving money (the crown's ledger); Basileia Romaion: 1337 (3618199037): bringing back a defined but absent country by handing it land (the Black and White Sheep, Imereti, the Turkish emirates); Refined Colonization (3816832717): an admission list for trading posts (colonisation); Manchu-Qing Flavour Expansion (满洲-清朝风味扩展, 3714561641): the structure of an appanage subject type (the touxia princes), a tribute audience that rules on the request and prices it by the other side's income and a subject's willingness to send troops (Goryeo), the army-granary province modifier and how province food is read (sea transport), inflation levels and the size of monthly inflation (paper money); National Destinies (3668193813): choose a path, then three stages, each with a checklist (the Yuan restoration); Praecepta Militaria - Propyrglon tou Dunabeos (3820674880): setting up and ending a one-way protection that is not vassalage (Serbia phases 2-3); Flavorium Universalis - Rhomania (3791634667): the keys and size of the "Silk Road reopened" modifier (Restoration and Hegemony, batch 3); MEIOU and Taxes (3735059838): reading inflation as a fraction (paper money). Engine behaviour recorded in the script comments of Celestial Empire Expansion (3810799047), the Praecepta Militaria series, The Persianate World and Rhomania - a Journey To The West helped us find and avoid several problems.

## Licence

See [LICENSE.md](LICENSE.md).
