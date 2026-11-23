# 凤凰计划测试版 Phoenix Beta（OEBYZ）v21.0

欧陆风云 5 的东罗马（拜占庭）与欧亚全时代重制 MOD 测试版，适配游戏版本 1.4.9，界面有中文和英文。测试版更新较频繁，可能会有 bug，但可以先体验最新内容。

> **v21.0 不支持旧存档：v20.0 及以前任何版本的存档都不能用于这一版，请新开一局。** 想继续旧档的玩家请玩正式版。2026-11-23 在 EU5 1.4.9 上分三轮实机测试（rc1→rc2→rc3）：1337 开局 13 组新探针（P10–P22）全部达到预期读数；观察者局 1337→1361（24 年，约 9 分钟）没有崩溃，本模组脚本运行期报错为 0（rc1 同一段约 17,000 行，来自法律 2.0）；金帐汗国 1337–1361 年拥有地块稳定在 409–414 块（rc1、rc2 都在 1343–1349 年崩到不足 100 块）。极乐洲新罗马（`ELR`）建国后，议会类型为“极乐新罗马元老院”，冷却结束后实际走通了“新君士坦丁堡 → 选择极乐议题 → 议会已召集”；投票结果没有等到。首轮查出的加载期与运行期问题（法律 `has_estate`、征讨败战回调、内阁行动语法与缺词条、总督区同色与人力效率等）已在 rc2/rc3 复测为 0。发版文件夹本身另做了加载检查：进主菜单，以拜占庭开局并推进数月，没有崩溃，本模组脚本运行期报错为 0。

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

## v21.0 主要内容《帝国经纬·全量深化版》

对比 v20.0：事件 `3,365 → 3,559`（`+194`），决议 `359 → 404`（`+45`），原生 `.dds` 美术与图标 `1,393 → 1,406`（`+13` 幅 1080×440 专属油画，另重绘 `44` 枚 512×512 成就双态图标），双语本地化各增 `+3,086` 条（中文 `55,024 → 58,110`，英文 `56,738 → 59,824`，增量 100% 对齐）；开局游戏规则 18 条、主线调度槽位 98/98 不变（所有 v21.0 周期逻辑均挂载于全局年度内核，零新增槽位）。

- **全局数值平衡审计与中度策略校准（模块 A）：** 新增全模组离线预算审计门禁（Rule 1–4 零违规），统一收口跨体系修正上限、特殊兵种限额与 44 项工场生产利润率（`<= 30%`）。
- **法律体系 2.0（模块 B）：** 新增 6 部通用帝国法典与 16 部区域文明专属法律，配套皇权/市民/教士阶层过渡联动与冷却机制，所有政策均带明确取舍而非单向堆数值。
- **拜占庭征讨与战区战役 2.0（模块 C）：** 围绕巴尔干、安纳托利亚、意大利、埃及与北非重写多阶段战役联动、胜利/受挫回调与补给统筹，衔接军区 2.0 与帝国权威。
- **人口同化与文化整合 2.0（模块 D）：** 深化四速有机同化与文化融合弧，补充城邦特许、边疆屯垦与多元容忍政策分支，平衡同化效率与阶层满意。
- **41 条 T2/T3 任务树、6 场中后期灾难与竞争性 AI（模块 E）：** 补齐 41 个二三线历史国家的专属任务树与 41 个高潮收官事件；新增 6 场中后期结构性灾难与防滚雪球竞争性 AI 联动。
- **6 套文明议会、24 项议程与 10 项内阁行动（模块 F）：** 面向欧亚主要文明新增 6 套特色议会与 24 项专属议题、10 项高价值内阁行动，并将专属附庸保护锁扩展至 27 类特殊附庸。
- **第四罗马《极乐洲新罗马》（`ELR`）核心修复与全量深化：** 修复脱壳建国后残余部落改革/特权与元老院无法召开问题，落实新大陆 75 年三段式经济成长曲线与极乐元老院专属议题。
- **金帐汗国防早崩与察合台三翼 17 埃米尔重制：** 修复金帐汗国 1337–1356 年因君主早逝触发原版 `-50` 团结度导致的反复崩盘（1357 年起撤去护盾，交还原版大混乱机制）；察合台汗国重构为东西三翼（新增 `FRG`、`OTR`、`BSB`）共 17 个埃米尔附庸体系。
- **12 个建筑型总督区与 4 大专门附庸体系：** 为德里苏丹国（5 伊克塔）、马穆鲁克（3 副王府 + 谢里夫国）、匈牙利（特兰西瓦尼亚沃伊沃德）、卡斯蒂利亚（2 骑士团/前沿督军区）与埃塞俄比亚（提格雷海王）实装原生建筑型总督区；深化札剌亦儿、格鲁吉亚、吐蕃、马里与高棉曼陀罗（`PHM`）专门附庸。
- **战略商品闭环、6 套局势 GUI、14 旗舰任务升级与美术抛光：** 打通精炼钢/外销瓷茶/工业化学品/航海天文钟与 5 大运河跨体系闭环，实装 6 套原生局势界面；升级 14 个 T1 旗舰国任务与 28 项高潮事件；补齐 13 幅 1080×440 专属油画与 44 枚重绘 512×512 双态成就图标。

### 可选子模组

可选子模组（均需排在主模组 `OEBYZ-Phoenix-v21.0` 之后加载）：
- **开局精选页 3.0**（24 国双页画廊）：沿用 v20.0 版，创意工坊 `3844347953`；没有和 v21.0 一起重新实测。
- **1453 / 1648 / 1776 三套独立剧本**还在修，本版不发布：实测时 1648、1776 的多位君主序号显示错误（如路易十四显示为路易十一），修好并复测后再单独发布。
- 原声带子模组仍不发布（无编译音频库）。

## v20.0 主要内容（整合 v15.0 / v15.5 / v16.0 / v16.5 / v17.0 / v17.5 / v18.0 / v18.5 / v19.0 / v19.5 / v20.0）

对比 v14.5：事件 `2,641 → 3,365`（`+724`），原生 `.dds` 美术与图标 `1,265 → 1,393`（`+128`），中英词条各 `46,623 → 56,797`（约 `+10,170`），开局游戏规则 18 条、主线调度槽位 98/98 不变。

- **全球内核与军区 2.0 续作（v15.0）：** 全局年度/月度调度内核与性能计数、5 个文明议会、10 项顶栏提醒、军区 2.0 第一阶段、1337 开局飞地整编（费拉德尔菲亚自由城等）、原版覆写从 74 个减到 40 个。
- **东亚群星（v15.5）：** 日本、大明 2、清 2、朝鲜、北元与东南亚四国的任务树与事件；大元 84 幅插图收口。
- **欧陆风云与星月铁骑（v16.0）：** 奥斯曼、西欧五强、中北欧的任务树与兵种；4 个原版国际组织与管区大督军区。
- **蒸汽、金融与帝国黄昏（v16.5）：** 蒸汽机商品与 9 级铁道、泡沫与金融危机灾难、独立浪潮、22 项成就、500 年遥测 3.0。
- **跨纪元与交响乐（v17.0）：** 非洲与美洲 5 条任务树、拜占庭 5 路强线与约翰七世尾声。
- **草原风暴与响应式世界（v17.5）：** 金帐、察合台、大元的飞地清理；察合台、格鲁吉亚、札剌亦儿、马拉塔任务树；16 个原生事件钩子驱动的响应式事件。
- **活阶层与小冰期（v18.0）：** 12 项多国国际组织表决、7 个文明议会；阶层私兵、阶层银行借贷、银行家族与日本建筑国的防断粮护栏；33 个游牧军队国的冬牧护栏；小冰期延冬与常平仓跨市买粮；王朝声望、摄政与太子教育。
- **双世纪剧本与战法和约（v18.5）：** 法国、波希米亚、云南梁王的大封建收拢；6 个原版国际组织深化；文化征召战法与 10 项和约条款。
- **战略商品、运河与 AI 3.0（v19.0）：** 精炼钢、外销瓷茶、工业化学品、航海天文钟 4 种商品与生产链；苏伊士、巴拿马、基尔、伏尔加—顿河、京杭大运河 5 项工程；6 个地图模式与 15 列国家账本；可选的后期减负助手；AI 3.0。
- **欧亚遗珠（v19.5）：** 立陶宛、诺夫哥罗德、苏格兰、阿拉贡、佛罗伦萨、瑞士、摩洛哥、吐蕃 8 国任务树，全模组合计 55 条任务树。
- **终极典藏版（v20.0）：** 政体动态国旗、12 项顶栏提醒、6 个决议分类、24 国开局简介卡、4 套可在百科里随时打开的新手教程、1836 编年史大结局；专属附庸保护锁（大元行省、都护府、宗王不能被改成普通附庸）；全模组兵种、刷兵与殖民内容按时代和科技加锁（离线审计 98 处 → 0）；书签子模组 3.0（24 国，见下）。
- **实机修正（v20.0-rc2 / rc3 / rc4）：** rc2 修掉首轮实机 11 类问题，并补齐 50 张商品修正图标；rc3 修掉 475 年长局里 1362 年以后才出现的 5 类空引用比较报错（改为 `?=`），给 3 处外交/宫廷脚本加了前置条件，并补齐开局精选页 3.0 的 24 条悬停提示；rc4 修好开局画廊第 2 页的翻页按钮（原来点了没反应），以及金帐汗国、奥地利、察合台、佛罗伦萨、摩洛哥 5 张卡片的空白国旗。

可选子模组：**开局精选页 3.0**（24 国，两页 3×4 画廊）在创意工坊条目 3844347953 更新，GitHub 附 ZIP；实机核对过两页 24 张卡片的国旗、悬停提示和翻页按钮，选卡后能以拜占庭开局。1453、1648、1776 三个剧本子模组还在制作，本版不发布。原声带子模组本版也不发布（没有编译好的音频库，游戏里放不出声）。

## v14.5 主要内容（整合 v11.8.2 / v12.0 / v12.2 / v13.0 / v13.5 / v13.6 / v13.8 / v14.0 / v14.5）

对比 v11.8：事件 `2,377 → 2,641`（`+264`），原生 `.dds` 美术与图标 `1,106 → 1,265`（`+159`），开局游戏规则 `17 → 18` 条，主线调度槽位 `93 → 98`（已排满），中英词条各增约 3,600 条。

- **大元帝国 3.0（v14.5）：** 原版红巾军局势面板里加入“至正平乱枢机仪”（平乱之势、朝议清浊、钞法与国库、京仓漕粮）和 9 项局势动作；红巾事件的免费兵团与大明起事重新标定；宗王 2.0（10 位投下宗王、五户丝抵扣岁赐、每王三项交互、三处亲王行府、上都库里台）；十一行省 2.0（外交容量占用 `3.00 → 0.45`、云南与征东并入、每省四项交互、12 个行省事件）。
- **极乐洲新罗马脱壳与 2.0（v11.8.2、v13.6）：** 西渡后改用独立国家标签 `ELR`，旧大陆视野清空，带走已研究的科技、君主与继承人，开国舰队 5 艘；6 个美洲与 4 个故土总督区、文兰与斯巴达尼亚两个可选风味国、两座御用工场、“双头大帝”迁都。
- **欧亚世界协调会、AI 性格与情境音乐（v12.0，开局规则 #18）：** 一个 1648 年以后的多边组织与 12 项国际组织决议；天朝 2.0 的 6 个事件与两项交互；6 套 AI 战略性格；按 14 个节点切换原版曲目的音乐调度和点播台。
- **帝国驿道署与殖民 3.0（v12.2）：** 只给玩家用的自动修路（真实扣款与工期，三种路由模式）；两座海外建筑、特许商社法、12 个殖民事件。
- **启蒙科学、非洲三轴与美洲三帝国（v13.0）：** 印刷与科学院（4 座地标、13 个事件）；埃塞俄比亚、马里与桑海、基尔瓦与大津巴布韦；阿兹特克、印加、易洛魁；8 个跨大洲事件。主线槽位排满 98/98。
- **大师与名作、16 项和约条款、制度细化与 12 国开局（v13.5）：** 8 类大师与 12 件名作、16 项和约条款、8 项部队技能、16 项名城宪章、8 套摄政、神道四派；12 个主角国家的开局剧本与开幕导览卡。
- **帝国柱石界面、天朝 3.0 与新任务（v13.6）：** 帝国柱石由 9 个页签并为 4 个，另有两部只读编年史；10 个大都护府与随朝代变化的国名；`ELR`、埃塞俄比亚、特诺奇蒂特兰、印加四套任务树（共 46 项）。
- **49 幅事件插画重绘（v13.8）：** v11.0 以后的 41 张程序占位图和 8 张新图换成了 1080×440 的历史题材油画风插画（AI 生成，经人工筛选和修整）。
- **终局与编年史（v14.0）：** 编年史里程碑扩到 22 项，新增 1836 年封卷事件；附属国忠诚度相关数值统一为 0–100 整数。
- 可选子模组 `OEBYZ-Phoenix-Bookmarks`（开新游戏时先显示十二主角画廊）只放在 GitHub Release 的附件里，没有上创意工坊；启用时要排在主模组之后。它的标题与旗帜修正同样没有复测；从画廊进局会带出原版教程的提示，关掉即可。

## v11.8 主要内容（整合 v10.0 / v10.5 / v11.0 / v11.2 / v11.5 / v11.8，并提前并入原定 v12.5 的内容）

对比 v9.9：事件 `1,946 → 2,377`（`+431`），决议 `140 → 228`（`+88`），原生 `.dds` 美术与图标 `888 → 1,106`（`+218`），开局游戏规则 `12 → 17` 条，主线调度槽位 `71 → 93`，中英词条各增约 6,400 条。

- **《第四奥德赛 · 极乐洲新罗马》（v10.5，可选，开局规则 #13）：** 君士坦丁堡陷落后（也可设为 1337 年提前启航，或整个关闭）率众西渡，在大洋彼岸登陆立国。四幕：圣火西渡与登陆、立国与元老院及极乐希腊文化、三教抉择（联动罗马多神教，新增 2 尊西海神祇与 10 项神谕）与新军团战舰、大西洋争霸与重返故土。57 个事件、10 项决议。
- **全欧亚六条主角线与 25 国任务（v10.0）：** 金帐与帖木儿、马穆鲁克、波兰—立陶宛、威尼斯与热那亚、大明双轨、女真与满洲六条 500 年主角线；欧亚经济 2.0 与教务 2.0；25 个国家各一套任务包，共 300 项任务，不覆写原版任务。134 个事件。
- **暗影、海洋、佣兵与历史大危机（原定 v12.5，提前并入；开局规则 #14）：** 谍报、宫廷密谋与王朝外交（5 项国家交互、3 项人物交互、6 项内阁行动）；私掠特许、海峡通行税等 3 种宣战理由与 5 次历史远航；雇佣兵契约与自由军团哗变灾难；小冰期与十六世纪白银价格革命两场灾难、12 项议会诉求和按史实写的叛军纲领。55 个事件。
- **近世疫病、后期霸权、终局大战与编年史（v11.0，开局规则 #15、#16）：** 1460–1750 年的两种近世疫病（黎凡特复发鼠疫、军营热）与双岛检疫港、陆疆封锁站；不覆写原版霸权的后期四维霸权与反霸张力；1750–1836 欧亚终局大战局势（四种结局）；典藏编年史与 1836 年评级；默认关闭的观察者年度数据导出。58 个事件、13 项决议。
- **天朝四海：分封、羁縻与都护（v11.2）：** 执掌天命的国家可以册封宗藩、设羁縻宣慰司与四海大都护府三类附属；4 部天朝法律、8 项外交交互、3 种宣战理由、按轨道变化的国名与官称，削藩与改土归流。24 个事件。
- **御用工场、区域产业、特色征召与军阵（v11.8）：** 6 座御用工场与 14 档可切换配方、6 项市场需求；6 个区域产业与 4 套用工制度；8 条序列 42 档特色征召兵（军区屯田兵、怯薛、射击军、哥萨克、西帕希、红头军、贵族总动员、曼萨布达尔）；4 陆 2 海共 6 种军阵与 4 套练兵法。
- **四大新战区（v11.5，开局规则 #17）：** 波斯与中亚、印度洋与次大陆、日本与朝鲜、西欧各有一座地标建筑、新法律、政府改革、阶层特权、4 项科技、4–5 项决议和 14 个事件，波斯与印度另有 5 个新宗教学派；通行证制度、抗通行证海盟、东行使团、渡海大战四件大事把四个战区连在一起。西欧这一线不需要任何扩展包。

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

- **先补测与修正：** 把这一版没有复测的修正（尤其是大元与大明的平衡）和没有逐项实测的内容（见“已知问题”）走一遍并修正；观察者长局跑到 1836 年。
- **持续：** 跟进欧陆风云 5 的版本更新，维护 1337 开局。

## 已知问题

- 本版不支持 v20.0 及更早版本的旧存档，请新开一局；只适配 EU5 `1.4.9`。
- 1337–1361 的观察者局里，金帐汗国在 1357 年撤去护盾后到 1361 年仍未出现原版大混乱；更晚的走向没有测。
- 主模组仍保留少量历史遗留加载提示（43 个后期融合文化开局无人口、若干早期版本的旧改革/特权图标提示等），均不影响正常游玩。
- 极乐洲新罗马建国事件（`oe_ely.13`）若玩家一直不选且取消暂停，超时后会自动留在旧大陆残余国家；正常手动点击“率众西渡”即可无缝切换至 `ELR`。
- 没有逐项实测的：6 套新局势界面视觉、13 张新油画与 44 张重绘成就图逐张核对、极乐新罗马议会投票结果与 75 年三段经济曲线、察合台 14 对 3 东西分裂细节、41 条 T2/T3 任务树与 6 场中后期灾难的逐个触发，以及开局精选页 3.0 与 v21.0 同时使用。

## 安装

- **Steam 创意工坊（推荐）：** 订阅上面的链接，然后在游戏的“模组和DLC”里把它加入播放集。
- **手动安装：**
  1. 下载 [Release](https://github.com/miscos330/OEBYZ-Phoenix/releases) 里的压缩包；
  2. 解压出 `OEBYZ-Phoenix-v21.0` 文件夹；
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

# Phoenix Beta (OEBYZ) v21.0 — English

The beta of an Eastern Roman (Byzantine) and Pan-Eurasian overhaul for Europa Universalis V, made for game version 1.4.9. The beta updates often and may contain bugs, but it has the newest content.

> **v21.0: Old saves are not supported: saves from v20.0 or earlier will not work with this version. Start a new game.** Tested live on EU5 1.4.9 on 23 November 2026 in three rounds (rc1→rc2→rc3): all 13 new 1337 probes (P10–P22) returned their expected values; an observer game 1337→1361 (24 years, about 9 minutes) ran with no crash and 0 runtime script errors from this mod (rc1 logged about 17,000 lines there, from Laws 2.0); the Golden Horde held 409–414 locations from 1337 to 1361 (in rc1 and rc2 it fell below 100 between 1343 and 1349). After founding Nova Elysia (`ELR`) the parliament type is the Elysian Senate, and once its cooldown ended a session was actually called at New Constantinople on an Elysian issue; the vote result was not awaited. The load-time and runtime issues found in the first round (Laws 2.0 `has_estate`, campaign defeat hook, cabinet action syntax and missing texts, viceroyalty colours and manpower efficiency, etc.) were re-tested at 0 in rc2/rc3. The release folder itself was load-checked: main menu, then a game as Byzantium run for some months with no crash and 0 runtime script errors from this mod.

- **Steam Workshop:** https://steamcommunity.com/sharedfiles/filedetails/?id=3667460405
- **GitHub:** https://github.com/miscos330/OEBYZ-Phoenix

⭐ **If you enjoy the mod, please star this repository.** Stars help other players find it and are the most direct encouragement for us. Bug reports are welcome in Issues.

## New in v21.0 (Empire Meridian)

Against v20.0: events `3,365 → 3,559` (`+194`), decisions `359 → 404` (`+45`), native `.dds` assets `1,393 → 1,406` (`+13` new 1080x440 bespoke event paintings, plus `44` redrawn 512x512 achievement icons), bilingual text `+3,086` keys per language (Chinese `55,024 → 58,110`, English `56,738 → 59,824`, 100% delta parity); 18 Game Rules and 98/98 mainline slots unchanged (all v21.0 periodic logic runs inside the global yearly kernel).

- **Global Balance Budget Pass (Module A):** added a full-mod balance auditor (Rules 1–4, 0 violations) enforcing moderate-strategy caps on modifiers, special unit limits and all 44 manufactory production methods (`<= 30%` markup).
- **Laws 2.0 Overhaul (Module B):** added 6 universal imperial codes and 16 regional civilization laws with crown/burgher/clergy transition effects and clear trade-offs.
- **Byzantine Reconquest & Campaigns 2.0 (Module C):** multi-stage campaign hooks across the Balkans, Anatolia, Italy, Egypt and North Africa with victory/setback effects linked to Theme System 2.0 and Imperial Authority.
- **Population Assimilation & Cultural Integration 2.0 (Module D):** deepened 4-speed organic assimilation and hybridization arcs with urban charter, frontier settlement and pluralism branches.
- **41 T2/T3 Mission Trees, 6 Mid/Late Disasters & Competitive AI (Module E):** added 41 regional mission trees with 41 climax events, plus 6 mid/late structural disasters and competitive anti-snowball AI hooks.
- **6 Civilization Parliaments, 24 Agendas & 10 Cabinet Actions (Module F):** added 6 distinct civilization parliaments with 24 agendas and 10 cabinet actions, and expanded the special-subject protection lock to 27 subject types.
- **Fourth Rome (`ELR`) Critical Fix & Deepening:** fixed residual tribal reforms/privileges and senate convocation after exodus, and added a 75-year 3-tier New World economic curve with bespoke Elysian Senate issues.
- **Golden Horde Early-Collapse Fix & Chagatai 3-Wing 17-Amir Overhaul:** fixed the repeated 1337–1356 Golden Horde collapse triggered by an early ruler death (`-50` unity hit); the shield is removed from 1357, handing back to the vanilla Great Troubles; rebuilt Chagatai into a 3-wing (`FRG`/`OTR`/`BSB`) 17-amir structure.
- **12 Building-Type Viceroyalties & 4 Specialized Vassal Systems:** implemented native building-type viceroyalties for Delhi (5 iqtas), Mamluks (3 niyabats + Sharifate), Hungary, Castile and Ethiopia, plus specialized vassals for Jalayirids, Georgia, Tibet, Mali and Khmer (`PHM`).
- **Strategic Goods Loop, 6 Situation GUIs, Flagship Missions & Art Polish:** closed the strategic goods and 5-canal loop with 6 situation GUIs, upgraded 14 T1 flagship mission trees with 28 climax events, added 13 bespoke 1080x440 event paintings and redrew all 44 512x512 achievement icons.

### Optional Submods

Optional submods (load strictly **after** `OEBYZ-Phoenix-v21.0`):
- **Bookmarks 3.0** (24-nation 2-page gallery): the v20.0 version, Workshop `3844347953`; not re-tested together with v21.0.
- The **1453 / 1648 / 1776 standalone scenarios** are still being fixed and are not part of this release: in testing, several rulers in 1648 and 1776 showed the wrong regnal number (Louis XIV appeared as Louis XI). They will be released separately once fixed and re-tested.
- The soundtrack submod remains unreleased (no compiled sound bank).

**Known issues:**

- Saves from v20.0 or earlier are not supported; start a new game. Built for EU5 `1.4.9` only.
- In the 1337–1361 observer game the Golden Horde had not entered the vanilla Great Troubles by 1361 after the shield was removed in 1357; later years were not tested.
- A few pre-existing load notes remain in the main mod (43 late-era hybrid cultures with no 1337 pops, legacy reform/privilege icon notes); none affect gameplay.
- In the Nova Elysia founding event (`oe_ely.13`), letting the event auto-timeout while unpaused keeps the player in the Old World remnant; clicking the exodus option switches cleanly to `ELR`.
- Not tested item by item: the look of the 6 new situation GUIs, each of the 13 new paintings and 44 redrawn achievement icons, the Nova Elysia parliament vote result and 75-year 3-tier curve, Chagatai 14-vs-3 split details, individual triggers of the 41 T2/T3 mission trees and 6 mid/late disasters, and Bookmarks 3.0 together with v21.0.

## New in v20.0 (v15.0 to v20.0)

Against v14.5: events `2,641 → 3,365` (`+724`), native `.dds` art and icons `1,265 → 1,393` (`+128`), text entries per language `46,623 → 56,797` (about `+10,170`); Game Rules (18) and main-line slots (98/98) unchanged.

- **Global kernel and Theme System 2.0 continued (v15.0):** a global yearly/monthly scheduler with performance counters, 5 civilisation parliaments, 10 top-bar alerts, Theme 2.0 phase 1, 1337 exclave clean-up (Free City of Philadelphia and others); vanilla overrides cut from 74 to 40.
- **East Asian stars (v15.5):** mission trees and events for Japan, Ming 2, Qing 2, Korea, Northern Yuan and four Southeast Asian states; the last of the 84 Yuan pictures.
- **Europe and the Crescent (v16.0):** mission trees and units for the Ottomans, the five great Western European powers and Central/Northern Europe; 4 vanilla international organisations and diocese super-themes.
- **Steam, finance and imperial twilight (v16.5):** steam engines as a good and a 9-tier railway, bubble and financial crisis disasters, independence waves, 22 achievements, 500-year telemetry 3.0.
- **Across eras and the symphony (v17.0):** 5 African and American mission trees, five Byzantine strong lines and a John VII epilogue.
- **Steppe storm and a reactive world (v17.5):** exclave clean-up for the Golden Horde, Chagatai and Yuan; Chagatai, Georgia, Jalayirid and Maratha mission trees; reactive events driven by 16 native event hooks.
- **Living estates and the Little Ice Age (v18.0):** 12 multinational resolutions and 7 parliaments; estate private regiments, estate bank loans, guard rails for banking houses and Japanese building states; winter-camp rails for 33 nomad army states; extended winters and cross-market grain purchases; dynasty prestige, regencies and heir education.
- **Two century scenarios, war doctrine and peace terms (v18.5):** great-fief consolidation for France, Bohemia and the Prince of Liang; 6 vanilla international organisations deepened; cultural levies and 10 peace terms.
- **Strategic goods, canals and AI 3.0 (v19.0):** refined steel, export porcelain and tea, industrial chemicals and marine chronometers with their production chains; Suez, Panama, Kiel, Volga-Don and Grand Canal projects; 6 map modes and 15 ledger columns; optional late-game helpers; AI 3.0.
- **Hidden gems of Eurasia (v19.5):** mission trees for Lithuania, Novgorod, Scotland, Aragon, Florence, Switzerland, Morocco and Tibet: 55 mission trees in the mod.
- **Definitive edition (v20.0):** dynamic government flags, 12 top-bar alerts, 6 decision categories, 24 start-country cards, 4 tutorial chains you can open from the encyclopedia at any time, an 1836 chronicle finale; a protection lock for special subjects (Yuan provinces, protectorates and princes cannot be turned into ordinary subjects); era and technology locks on units, spawned armies and colonial content across the mod (offline audit 98 → 0); Bookmarks submod 3.0 (24 countries, see below).
- **Live fixes (v20.0-rc2 / rc3 / rc4):** rc2 fixed the 11 initial live issues and added 50 goods modifier icons; rc3 fixed 5 kinds of empty-scope comparison errors that only appeared after 1362 in the 475-year game (now `?=`), added conditions to 3 diplomacy/intrigue scripts, and added the 24 Bookmarks 3.0 hover texts; rc4 fixed the gallery's page 2 button (clicks did nothing) and the blank flags on 5 cards (Golden Horde, Austria, Chagatai, Florence, Morocco).

Optional submods: **Bookmarks 3.0** (24 countries on two 3 x 4 pages) is updated on Workshop item 3844347953 and attached to the GitHub release; both pages were checked live: all 24 flags, the hover texts and the page buttons work, and picking a card starts a game (tested with Byzantium). The 1453, 1648 and 1776 scenario submods are still in progress and are not part of this release. The soundtrack submod is not released either (it has no compiled sound bank, so nothing plays in game).

**Known issues:**

- The longest observer game reached 1812; later content (the final war, the 1836 chronicle) has not appeared in a long game.
- In observer games the Golden Horde collapses around 1345, recovers, and collapses again after 1355 (the same in the four v14.5 games; cause unknown).
- When mercenaries are raised in Central Asia or Korea the log shows an engine note that no heavy infantry unit is available (not shown to come from this mod).
- The package still carries a few dozen old reform and privilege icons from v14.5 whose entries no longer exist; the load log notes that these icons have no matching object. This does not affect play.
- 13 new event pictures temporarily reuse existing paintings; new ones will follow.
- Not tested item by item: the visibility of every decision (only the offline era-lock audit, 0 findings, backs it), each country's mission tree and each v15–v20 event, and how the rc3 fixes behave after 1362 in a long game.

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

## Highlights of v14.5 (v11.8.2, v12.0, v12.2, v13.0, v13.5, v13.6, v13.8, v14.0, v14.5)

Against v11.8: events `2,377 → 2,641` (`+264`), native `.dds` art and icons `1,106 → 1,265` (`+159`), Game Rules `17 → 18`, main-line slots `93 → 98` (all used), about 3,600 more text entries in each language.

- **Great Yuan 3.0 (v14.5):** a pacification gauge (momentum, court opinion, paper money and treasury, capital granary) and 9 situation actions inside the vanilla Red Turban situation panel; the free regiments of the Red Turban events and the rise of the Ming re-tuned; Princes 2.0 (10 appanage princes, silk-household income set against the yearly grants, three interactions per prince, three garrison princely offices, the Shangdu kurultai); Eleven Provinces 2.0 (diplomatic capacity use `3.00 → 0.45`, Yunnan and Zhengdong added, four interactions per province, 12 province events).
- **Nova Elysia: a country of its own, and 2.0 (v11.8.2, v13.6):** after the crossing the realm becomes the new tag `ELR`, the Old World map knowledge is cleared, researched advances, ruler and heir come along and the founding fleet has 5 ships; 6 American and 4 homeland exarchates, the optional flavour countries Vinland and Spartania, two imperial manufactories, the two-headed emperor's move of the capital.
- **Eurasian Concert, AI characters and situational music (v12.0, Game Rule #18):** a multilateral organisation after 1648 and 12 international-organisation resolutions; 6 events and two interactions of Celestial 2.0; 6 AI strategic characters; a music director that switches vanilla tracks at 14 moments, with a jukebox.
- **Imperial Road Office and Colonisation 3.0 (v12.2):** automatic road building for the player only (real cost and build time, three routing modes); two overseas buildings, a chartered-company law, 12 colonial events.
- **Enlightenment science, three African axes and three American empires (v13.0):** printing and academies (4 landmarks, 13 events); Ethiopia, Mali and Songhai, Kilwa and Great Zimbabwe; the Aztecs, the Inca, the Iroquois; 8 cross-continent events. All 98 main-line slots are now used.
- **Masters and masterpieces, 16 treaty clauses, institutions and 12 starts (v13.5):** 8 kinds of masters and 12 masterpieces, 16 peace-treaty clauses, 8 unit abilities, 16 city charters, 8 regencies, four Shinto schools; start scenarios and day-one briefing cards for 12 protagonist countries.
- **Pillars of Empire screen, Celestial 3.0 and new missions (v13.6):** the Pillars panel goes from 9 tabs to 4, with two read-only chronicles; 10 grand protectorates with names that follow the dynasty; four mission trees (46 missions) for `ELR`, Ethiopia, Tenochtitlan and the Inca.
- **49 event pictures redone (v13.8):** the 41 procedurally drawn placeholders added since v11.0 and 8 new pictures are now 1080×440 history paintings (AI-generated, selected and retouched by hand).
- **Endgame and chronicle (v14.0):** 22 chronicle milestones and a closing event in 1836; subject-loyalty values unified to whole numbers 0-100.
- The optional submod `OEBYZ-Phoenix-Bookmarks` (a gallery of the twelve protagonists when starting a new game) is only attached to the GitHub release, not on the Workshop; load it after the main mod. Its title and flag fixes were not re-tested either; starting from the gallery brings up the vanilla tutorial prompts, which can be closed.

## Highlights of v11.8 (v10.0, v10.5, v11.0, v11.2, v11.5, v11.8, and the content planned as v12.5)

Against v9.9: events `1,946 → 2,377` (`+431`), decisions `140 → 228` (`+88`), native `.dds` art and icons `888 → 1,106` (`+218`), Game Rules `12 → 17`, about 6,400 more text entries in each language.

- **Fourth Odyssey: Nova Elysia (v10.5, optional, Game Rule #13):** After the fall of Constantinople (or from 1337, or switched off) the Romans sail west and found a state across the ocean. Four acts: the voyage and landing; the new state, its senate and Elysian Greek culture; the choice between three faiths (tied to Religio Romana, with 2 new deities and 10 omens) and new legions and warships; the struggle for the Atlantic and the return home. 57 events, 10 decisions.
- **Six Pan-Eurasian protagonist lines and missions for 25 countries (v10.0):** 500-year lines for the Golden Horde and the Timurids, the Mamluks, Poland-Lithuania, Venice and Genoa, a Ming dual track, and the Jurchen and Manchu; Eurasian economy 2.0 and church affairs 2.0; one mission pack for each of 25 countries, 300 missions in all, with no vanilla mission overwritten. 134 events.
- **Shadows, seas, mercenaries and historical crises (planned as v12.5, brought forward; Game Rule #14):** Espionage, court plots and dynastic diplomacy (5 country interactions, 3 character interactions, 6 cabinet actions); letters of marque, strait tolls and 2 more casus belli, and 5 historical voyages; mercenary contracts and a free-company mutiny disaster; the Little Ice Age and the price revolution as two disasters, 12 parliament demands and historically based rebel programmes. 55 events.
- **Early modern epidemics, late hegemony, the final war and the chronicle (v11.0, Game Rules #15 and #16):** Two diseases of 1460–1750 (the recurring Levantine plague and camp fever) with lazarettos and land cordons; a four-dimensional late hegemony that does not overwrite the vanilla hegemons; the Eurasian final war of 1750–1836 as a situation with four endings; a keepsake chronicle and an 1836 rating; an observer data export that is off by default. 58 events, 13 decisions.
- **The Celestial realm: enfeoffment, loose-rein offices and protectorates (v11.2):** The holder of the Mandate can create three kinds of subject (vassal kings, pacification offices, grand protectorates), with 4 Celestial laws, 8 diplomatic interactions, 3 casus belli, and country names and titles that change with the dynasty's track. 24 events.
- **Imperial manufactories, regional industries, special levies and formations (v11.8):** 6 imperial manufactories with 14 switchable recipes and 6 market demands; 6 regional industries and 4 employment systems; 42 tiers of special levies in 8 lines (thematic soldier-farmers, keshig, streltsy, cossacks, sipahis, Qizilbash, the noble levy, mansabdars); 6 formations (4 land, 2 naval) and 4 recruitment methods.
- **Four new theatres (v11.5, Game Rule #17):** Persia and Central Asia, the Indian Ocean and the Subcontinent, Japan and Korea, and Western Europe each get a landmark building, new laws, government reforms, estate privileges, 4 advances, 4–5 decisions and 14 events; Persia and India also get 5 new religious schools. Four world events (the pass system, the league against it, the mission to Asia, the war across the strait) tie the theatres together. The Western European line needs no expansion.

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

- **First, test and fix:** re-test the fixes of this version (above all the Yuan and Ming balance), walk through what was not checked item by item (see Known issues) and run an observer game to 1836.
- **Ongoing:** keep pace with Europa Universalis V patches and maintain the 1337 start.

## Known issues

- Old saves are not supported; start a new game. Game version 1.4.9 only.
- **The fixes of this version were not re-tested in game.** The largest is the balance between the Yuan and the Ming: in the four observer runs of the previous candidate the Ming was annexed whole by the Yuan between 1364 and 1372 and the Yuan always survived. This version changes the Yuan's levy and upkeep modifiers during the Red Turban years, gives the AI-controlled Yuan a fork between a firm court and factional decay, and strengthens the rise of the Ming; how games now turn out has not been looked at.
- **The longest observer run reached 1463** (one run of the v14.0 candidate); the four runs of v14.5 reached 1380-1390. Content that appears later (theatre events after 1500, the early modern epidemics from 1460, the final war from 1750, the closing of the chronicle in 1836) never came up in a long run.
- **Only fired from the console or spot-checked, never walked through as a player:** the 12 Concert resolutions one by one, the Celestial 2.0 events, the 6 AI characters; the three routing modes of the Road Office and the roads actually laid on the map, the Colonisation 3.0 events; most events of v13.0; masters and masterpieces, the 16 treaty clauses, city charters, unit abilities, regencies; the Ming and Qing titles of Celestial 3.0 and the four new mission trees; the options of the Yuan events such as the Shangdu kurultai and the dismissal at Gaoyou.
- Never tested without the official expansions (the mod is designed not to need them; all five are installed on the test machine).
- Situational music: the script no longer logs errors, but nobody has checked that tracks really switch.
- The 49 redone pictures are AI-generated, then selected and retouched by hand.
- Opening the Pillars of Empire panel, or switching to another country, adds a few thousand interface errors to the log at once (an old problem; play is not affected). A Yuan game shows some thirty exclusive-trade reports in its first month (vanilla month-end behaviour).
- The yearly observer data export (Game Rule #16) is off by default.
- Hindu countries have no school picker, so the two new Hindu schools are adopted in the event The Great Festival at Srirangam; the school of the Samarkand tables can be adopted in the event The Star Tables Completed.
- Still in the log: some new diplomatic interactions have no message type and some prices have no modifier type; neither affects play. Several script errors come from vanilla files, not from this mod.
- Themes (building-type countries) cannot recruit regulars themselves: an engine rule, as for the Hansa.

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
