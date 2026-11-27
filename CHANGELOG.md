# 《凤凰计划（OEBYZ）》v60.0 更新日志（合并 v56.0–v60.0 五大里程碑 + 律法瘦身重构）

> **发布状态**：v60.0（适配 EU5 1.4.9），合并 **v56.0 至 v60.0** 五个大版本的全线修复、深度拓展、架构瘦身与中英 Wiki 对齐。
> **存档提示**：v60.0 **不兼容旧版本存档**，请新开一局。
> **官方音乐子模组**：[《凤凰计划 · 历代交响原声》（Project Phoenix Soundtrack，工坊 ID `3846593343`）](https://steamcommunity.com/sharedfiles/filedetails/?id=3846593343) — 60 首罗马与地中海交响原声（约 148 分钟），不改联机校验，保持独立兼容。

制作：寐夜空灵、miscos330

---

## 一、中文更新日志

### 1. 律法架构瘦身与原版 `INJECT:` 深度整合（主模组 + 编年史，v60.0 方案 B）

针对玩家反馈的“自定义通用法律偏多、与原版法律及阶层特权重叠”以及“1337 拜占庭开局被锁在封建采邑征召”，彻底重构通用与地区律法架构：
- **移除 7 条重叠独立法律**：删去 `oe_lw2_labor_mobility_law`（劳役农奴迁徙法）、`oe_lw2_military_service_law`（常备军与兵役法）、`oe_lw2_judicial_code_law`（司法与法典体系）、`oe_lw2_press_academy_law`（新闻出版与学府法）、`oe_lw2_maritime_commerce_law`（海事与特许贸易法）、`oe_sci_press_charter_law`（重复出版法）与英格兰重复普通法 `oe_lw2_eng_common_law`，同时彻底清理古典 6 纪元（361–768）开局 35 处旧兵役法引用。
- **15 项特色政策无缝并入 6 条原版 EU5 法律（`INJECT:` / `REPLACE:`）**：
  - `medieval_levy_law`（原版征召兵法）：并入 **军区与边疆屯田世兵制（`oe_lw2_pol_frontier_colonies`）**，**1337 开局即对拜占庭、军区制国家、希腊/中华/波斯/突厥文化圈开放可选**（其余国家大航海时代解锁）。
  - `recruitment_law`（原版征兵法）：并入特许雇佣兵团与全民义务征兵制。
  - `press_law`（原版出版法）：整合全部 5 项近代印刷与学府政策（含 3 项原科学革命出版宪章）。
  - `maritime_law`、`peasants_rights_laws` 与 `legal_code_law`：并入重商航海条例、圈地工场与法定劳工保护、行政法院/近代民法典与英格兰人身保护令/权利法案。
- **帝国财税与预算总法（`oe_lw2_fiscal_budget_law`）升级为开局三选一**：保留包税承包制，开放官僚帝国/大帝国开局即选「官僚清丈田赋」，并新增「市镇关榷与商帮协定」作为市民/海港路线 Day-1 选项（共 5 项，后 2 项按宗教改革/革命时代解锁）。
- **地区律法去重与年代门控**：俄国农奴法典门控至 `>= 1480`；1337+ 金帐/帖木儿与印度主角去除与原版/专线的双札撒/双曼萨布达尔重叠。全库校验 295 条法律、1,149 项政策 `0` 重名。

### 2. 全纪元顺序统一、1337 前防串代与 1204 大蒙古国大修（编年史 + 主模组，v56.0）

- **11 纪元顺序统一（361–1756）**：合并 `in_game/common/age/00_default.txt`，彻底消除 1204 开局时代序倒置导致的“达延汗分封”等后世决议/法条泄漏，同时为全部北元与后世决议/法律补齐严格年代门控。
- **1204 大蒙古国历史分封、忽里勒台承嗣与改革上限修复**：
  - 全 948 个编年史游牧/部落开局国家（含 1204 大蒙古国 `MGE`）王室改革严格收束至 `<= 1/1`（1204 蒙古开局精准 `1/1`）。
  - 四大分封（东道斡赤斤 `M5A`、钦察术赤汗国 `GLH`、察合台汗国 `CHG`、窝阔台汗国 `M5C`）精确锁定历史宗王（**帖木哥斡赤斤 / 术赤 / 察合台 / 窝阔台**），杜绝挑错人与重名，并为后世配齐塔察儿/拔都/合剌旭烈兀/贵由兜底继承人；修正“术赤汗国汗国”与伊儿汗国形容词重复后缀；1204 钦察正名为“钦察-库曼联盟”不再与金帐混淆。
  - 新增专属 **忽里勒台大汗宗王承嗣制（`oe_v53_mgl_kurultai_succession`，`allow_foreign_ruler = no`）** 与分封即时继位人交接逻辑：已受封出镇独立兀鲁思的汗王不再兼任大蒙古国继承人，分封术赤/窝阔台后自动按历史顺位将大汗继承人顺延给留驻本廷的窝阔台或拖雷。
- **第四罗马防坐牢与第三奥德赛重构**：修复 1444 拜占庭改革数（`5/6`）与卡死瓶颈，补齐 24 条新世界节奏事件、8 项决议、4 座新建筑与精确校准 30% 利润率的赫斯佩里亚紫锦工坊。

### 3. 九大历史宗教神系与圣地、泛欧亚丝路与 13 条编年史旗舰任务树（v57.0–v58.0）

- **9 大历史宗教完全体（v57.0）**：为迦克墩、阿里乌派、海岛基督教、多纳图派、圣像破坏派及斯拉夫/凯尔特/日耳曼/前伊斯兰阿拉伯多神教配齐 32 座专属圣地、5 大多神教神祇殿堂与 **6 项普世公会议行动**（含 768 圣像破坏派东罗马完整开放 6 项行动）。
- **泛欧亚丝路与香料走廊局势 + 925 条六大文明动态地名（主模组 v58.0）**：覆盖拉丁语（175）、汉语官话（164）、阿拉伯语（167）、波斯语（130）、突厥语（153）与东斯拉夫语（136）共 925 条动态地名，零碰撞通过 `R65`。
- **编年史 13 条旗舰引导任务树（v58.0）**：为 361 尤里安、395 东西罗马、532 查士丁尼、632 大唐与哈里发、768 查理曼、1204 蒙古与尼西亚、1444 第四罗马、1648 南明/清、1776 乾隆/北美与 1821 希腊等新增 13 条完整 DAG 任务树（106 项引导任务）。
- **全球薄弱纪元与文明大补全（v58.0–v59.0）**：
  - **古典晚期（395/476/632/768）**：新增《395 斯提里科、阿拉里克与冰封莱茵河》《793 林迪斯法恩与维京时代黎明》2 个高清 `1080×440` 局势、36 条历史事件、6 座地标建筑与 6 项改革；同步补齐阿克苏姆、笈多与大和内容。
  - **1337 第二波十大经典国 + 东南亚与撒哈拉以南非洲 + 高加索草原**：深度拓展威尼斯、热那亚、波兰、朝鲜、德里、毗奢耶那伽罗、阿兹特克、印加等 10 国；补全吴哥/蒲甘/素可泰/马六甲/刚果/大津巴布韦/斯瓦希里/索马里 2 大局势与 36 条事件；新增 1204 塔玛尔女王格鲁吉亚与花剌子模局势、1204 伊比利亚再征服与腓特烈二世局势、瓦拉几亚/摩尔达维亚及准噶尔/哈萨克专线。
  - **1821 拉美独立、意大利复兴、十二月党人与幕末维新（v59.0）**：新增拉美解放者局势（含墨西哥/大哥伦比亚/巴西等双进度条与 4 项互动行动）及欧洲民族复兴与日本幕末链。

### 4. 原版机制深度扩容、美术去重、Glorp UI 清理与 86/86 硬门禁（v59.0–v60.0）

- **全面接入 EU5 原生机制**：新增 12 项世界城市宪章（`town_rights`）、8 项带 `@trigger_no!` 规范提示的角色交互、6 项新兵种技能（全 20 项自定义兵种技能动态写入 `loading_screen/input_profile/oe_unit_abilities.profile`，热键报错归零）、议会议题与议程、8 个骑士修会、12 件世界杰作、4 场历史灾难与霸主敕令。
- **美术与 GUI 质量清零**：
  - 全部 64 组主模组重复 DDS 卡片彻底去重至 `0`；**100% 自定义局势（主模组 + 编年史共 86 个）全部配齐专属 `.gui` 面板**。
  - 根治 `gen_v580` 的 136 字节 DDS 头偏移 bug，修复主模组 18 张 + 编年史 20 张 = **38 张** v58 贴图（彻底消除 395/768 局势与 1337 建筑图标紫噪点），并将 395/768 横幅全面升级为 `1080×440` 贴合时代的高清画面。
  - 清理 Glorp UI 重复 `blockoverride`、`economy_lateralview.gui` 重复 `visible` 与无效热键引用。
- **性能优化、英文 Wiki 全对齐与 86/86 引擎门禁**：
  - 新增 `R79–R86` 八条引擎硬门禁（`172/172` 自测通过）：覆盖兵种技能 profile、100% 局势 GUI、纪元年代顺序、游牧/拜占庭开局改革上限、宗教圣地神祇、禁用抽象 `empty=yes` 刷兵、3 通道纹章 `color3`、禁用裸 `age >=`、生产方式校验、全开局 `10_countries.txt` 法律校验与全部 DDS 128 字节头校验。
  - GitHub Wiki 同步上线 **10 页完整英文指南**，与中文 Wiki 全面对齐。

### 5. 实机验收汇总（2026-11-27，EU5 1.4.9）

- 经 `rc1 → rc2 → rc3` 三轮实机验证（0 CTD）：加载期较 `rc1` 清除全部 29 条报错且新增 `0` 条；`1204` 蒙古改革 `1/1`、四大兀鲁思精准绑定帖木哥斡赤斤 / 术赤 / 察合台 / 窝阔台、「术赤汗国」国名正常；`1337` 拜占庭方案 B 无重复法律、「军区与边疆屯田世兵制」开局即选、财税总法开局三选一；`768` 东罗马普世公会议 6 项行动全显示；`395`/`768`/`1204`/`1821` 五大新增局势面板与 395/768 图标横幅全部正常显示无报错；`rc4` 追加蒙古忽里勒台承嗣制（`O1`）与 395 莱茵古典横幅（`O2`）并全部通过 86/86 离线严检。
- **已知与后续规划（v61.0）**：成吉思汗及古典/近代 3D 肖像服饰重构（需独立去清化贴图与专用 3D `.mesh`）与长事件标题排版治理已明确排入 `v61.0` 头号里程碑。

---

## 二、English Changelog

> **Status:** v60.0 (EU5 1.4.9), combining all five milestones **v56.0–v60.0** plus the Plan B Laws Architecture Overhaul and full English Wiki parity.
> **Saves:** v60.0 is **not** compatible with older saves. Please start a new game.
> **Companion Soundtrack Submod:** [Project Phoenix Soundtrack (`3846593343`)](https://steamcommunity.com/sharedfiles/filedetails/?id=3846593343) — 60 Roman & Mediterranean symphonic tracks (~148 min), checksum-safe.

Made by: 寐夜空灵, miscos330

- **Laws Architecture Slimming & Native Vanilla `INJECT:` Consolidation (Plan B):** Removed 7 overlapping standalone universal/regional laws and 35 legacy classical setup law refs; folded 15 distinct policies cleanly into 6 native EU5 laws (`medieval_levy_law` with Day-1 Theme / Frontier Military Colonies for BYZ/Greek/Chinese/Iranian/Turkic realms, `recruitment_law`, `press_law`, `maritime_law`, `peasants_rights_laws`, and `legal_code_law`); upgraded Fiscal Budget Law to 3 balanced Day-1 choices (295 laws / 1,149 policies verified 0 duplicates).
- **Chronological Age-Order & Pre-1337 Anti-Leakage (v56.0):** Unified all 11 ages (`361–1756`) in `00_default.txt`, sealed Northern Yuan & late-era laws from 1204, capped all 948 Chronicles hordes/tribes to `<= 1/1` opening reforms (1204 MGE `1/1`), fixed 1444 BYZ `5/6` reforms, and overhauled Fourth Rome anti-prison pacing.
- **1204 Great Mongol Empire Enfeoffment & Kurultai Succession Overhaul (v56.0 & v60.0):** Bound the four great appanages (`M5A` Otchigin, `GLH` Jochi, `CHG` Chagatai, `M5C` Ögedei) to their exact historical Borjigin princes with non-duplicate late heirs (Taghachar / Batu / Qara Hülegü / Güyük), fixed Jochid/Ilkhanid duplicate title suffixes, and added bespoke `oe_v53_mgl_kurultai_succession` (`allow_foreign_ruler = no`) plus automatic Ögedei/Tolui heir handoff so enfeoffed vassal khans never remain heir to the Great Khaganate.
- **9 Historical Religions Full Mechanics, Silk Road & 13 Chronicles Flagship Mission Trees (v57.0–v58.0):** 32 holy sites, 5 pagan pantheons, 6-action Ecumenical Councils (open to 768 Iconoclast ERE), Pan-Eurasian Silk Road Situation, 925 6-civilization dynamic place names (Latin, Mandarin, Arabic, Persian, Turkish, East Slavic), and 13 guided Chronicles flagship mission trees (106 tasks).
- **Global Era Expansions & Native Mechanics (v58.0–v59.0):** 395 Frozen Rhine & 768 Viking Dawn HD situations, 1337 Wave-2 10 nations, Southeast Asia & Sub-Saharan Africa (2 situations, 36 events), 1204 Queen Tamar Georgia / Khwarazm / Reconquista & Frederick II, 1821 Libertadores / Risorgimento / Decembrists / Bakumatsu, 12 World Town Charters, 8 Character Interactions, 20 registered Unit Abilities (`oe_unit_abilities.profile`), Parliaments, 8 Chivalric Orders, 12 Masterpieces & 4 Disasters.
- **Zero Duplicate DDS, 100% Bespoke Situation GUIs, Complete English Wiki & 86/86 Strict CI:** Cleared 64 duplicate DDS card clusters to `0`, fixed the 136-byte DDS header offset across 38 v58 textures (eliminating purple-noise icons), upgraded 395/768 situation banners to crisp `1080×440`, added 10 full English Wiki guide pages, and enforced `86/86 R01–R86` CI rules (`172/172` selftests).

# 《凤凰计划（OEBYZ）》v55.0 更新日志（合并 v51.0–v55.0 + 历代交响原声子模组）

> **发布状态**：v55.0 正式版（EU5 1.4.9），合并 **v51.0 至 v55.0** 五个大版本的全部重构与修复。候选版 `v55.0-rc1` 至 `rc4` 于 2026-11-27 在 EU5 1.4.9 上经过四轮实机验收；发布包即实测通过的 `rc4`，模组脚本文件未再改动（仅更新主模组 `README.md`）。
> **存档提示**：v55.0 **不兼容旧版本存档**，请新开一局。
> **全新官方音乐子模组上线**：[《凤凰计划 · 历代交响原声》（Project Phoenix Soundtrack，工坊 ID `3846593343`）](https://steamcommunity.com/sharedfiles/filedetails/?id=3846593343) — 60 首罗马交响与地中海乐章（约 148 分钟），无缝融入 EU5 原版动态音乐系统，保留全部原版曲目、统一响度、不改变联机校验，可独立运行或搭配《凤凰计划》全系列使用。

制作：寐夜空灵、miscos330

---

## 一、中文更新日志

### 0. 全新官方子模组：《凤凰计划 · 历代交响原声》（工坊 ID `3846593343`）

- **60 首罗马与地中海交响原声（约 148 分钟）**：全部完成响度均衡并转码为 EU5 1.4.9 原生 Wwise 格式，无缝加入原版动态音乐池（原版曲目全部保留，新曲约占战争与和平轮播的四成）。
  - **战争乐章（14 首）**：《高举鹰旗》《匈人铁骑》四章、《草原之鞭阿提拉》《宣战号角》《冲锋战吼》等。
  - **和平与帝国组曲（37 首）**：《万城之皇君士坦丁堡》《奥古斯都》《狄奥多西大帝》《生于紫室》、北方诸岛，以及爱琴海、马格里布、伊比利亚、丝绸之路等地中海与近东乐章。
  - **拜占庭文化专属（19 首）**：宫廷、圣咏与君士坦丁堡主题曲（拜占庭文化国家约三分之一轮次切入播放）。
- **零侵入与联机安全**：全部文件位于 `loading_screen` 目录下，不改游戏脚本、不改联机校验；建议音频设置选择“动态 - 全部（Dynamic - All）”。
- **实机音频验收**：已在 EU5 1.4.9 实机加载验证 `0` 音频/Bank 报错，并通过实时音频录制与声学指纹比对确认新曲目正常播音（含第 1 曲与第 47 曲《极乐原野》）。

### 1. 532 查士丁尼光复深度重做（全时代编年史，v55.0）

- **三战区专属光复宣战理由（CB）**：贝利撒留北非远征、贝利撒留/纳尔塞斯意大利远征与利贝里乌斯西班牙远征改用三套专属光复 CB（`cb_oe_v55_532_vandalic_reconquest` / `gothic_reconquest` / `spania_reconquest`），直指核心战区，告别低效碎地割让。
- **战分 + 关键名城自动受降决胜**：
  - **阿非利加战区（汪达尔）**：占领迦太基且战分达 55% 即触发《帕普阿山受降：汪达尔王国覆灭》，连同撒丁岛、科西嘉岛（全部 8 城）与巴利阿里群岛一并划归东罗马/阿非利加总督区，彻底终结汪达尔政权；
  - **意大利战区（东哥特）**：占领罗马与拉文纳且战分达 60% 即触发拉文纳受降整区交割；
  - **西班牙战区（西哥特）**：占领科尔多瓦、塞维利亚、卡塔赫纳且战分达 45% 即触发南西班牙割让建置。
  - **战后 10 年停战保护**：若战败国在核心战区之外仍有残余领土（如北西班牙西哥特），受降议和后自动由东罗马与接收方施加 10 年停战，防止立刻回马枪。
- **东哥特王国正名与全事件因果门控**：
  - 532 意大利正式锁定为历史上的**东哥特王国（`FXO`）**，不再误显“意大利王国”。
  - 为 532 全部叙事事件（托提拉复起、拉文纳哥特王冠、纳尔塞斯赴意、国事诏书等）补齐严格战局因果条件，彻底杜绝“还没收复东哥特就弹出战后复起/治理事件”的时序错乱。

### 2. 全 11 剧本历史宗教大改（全时代编年史，v55.0）

彻底清零 1054 东西教会大分裂之前的早产“天主教”、用“清洁派”借壳的日耳曼部落以及东欧错配的波罗的海多神教，新增 **9 个完整历史宗教**（含图标、教义特质、神学机制与双语文案）：

- **迦克墩大公教会（`oe_rel_chalcedonian`）**：覆盖 361–768 东西罗马、法兰克与 589 年后西哥特等全部尼西亚—迦克墩正统基督教世界；跨过 1054 年后可走历史**东西教会大分裂**事件链，或由强盛统一罗马主动**弥合大分裂**！
- **阿里乌派基督教（`oe_rel_arianism`）**：真实还原 361–532 东哥特、西哥特、汪达尔、勃艮第、格皮德与伦巴第上层统治者与罗马迦克墩臣民的宗教二元张力。
- **凯尔特海岛基督教（`oe_rel_insular`）**：476–768 爱尔兰、威尔士、苏格兰、布列塔尼与早期诺森布里亚修院传统（附 664 惠特比宗教会议抉择）。
- **多纳图派（`oe_rel_donatism`）**：361–632 努米底亚与北非内陆基督教分支。
- **圣像破坏派（`oe_rel_iconoclasm`）**：768 君士坦丁五世朝廷与安纳托利亚军区（附 787 第二次尼西亚公会议抉择）。
- **斯拉夫多神教（`oe_rel_slavic_pagan`）**：361–768 波兰、波西米亚、罗斯、乌克兰、白俄罗斯与早期巴尔干内陆（`romuva` 回归波罗的海本体）。
- **凯尔特德鲁伊教（`oe_rel_celtic_pagan`）**、**大陆日耳曼多神教（`oe_rel_germanic_pagan`）**、**前伊斯兰阿拉伯多神教（`oe_rel_arab_pagan`）**。

### 3. 全剧本与 1337 动态省会直占 + 战分自动决胜引擎（主模组 + 编年史，v55.0）

- **大厅游戏规则开关（`oe_v55_gr_dynamic_province_seizure`）**：默认开启“**省会直占 + 自动受降**”，亦可在开局大厅自由切换为“仅单格直占”或“关闭（回归传统和约）”。
- **攻陷省会直占全行省**：
  - 覆盖**编年史全 12 剧本**全部远征/历史决战 CB，以及 **1337 主模组** 14 项讨伐/光复 CB、拜占庭九大光复战区、5 套原版重大冲突局势（含百战、红巾、帖木儿等）与通用“颁布讨伐檄文”决议。
  - 占领敌方**行省首府**即刻将该行省内所有敌属地块划归己方，同时严格排除盟友、中立国与内战，杜绝误吞。
- **人类防守方严格豁免保护**：
  - AI 进攻方攻陷**玩家**的地区首府时，**仅划转该首府单个地块**（绝不整省瞬吞玩家领土），并照常弹出警示事件；
  - 玩家进攻 AI 与 AI 互打保留完整“占领省会直取整省”。
- **战分 + 首都自动决胜**：对 AI 敌国达成“占领敌都且战分 ≥ 65%”或“战分 ≥ 80%”时弹出三选一受降事件（整区/全线收地、纳降称臣、或拒绝继续常规和谈）；人类防守方绝不会被强制投降。

### 4. 1204 尼西亚 / 伊庇鲁斯 / 特拉比松收复君堡 4 层核心修复（全时代编年史，v55.0）

针对社区反馈的“1204 尼西亚打回君士坦丁堡不给核心”，按 EU5 1.4.9 原版 `add_core` + `change_integration_level = core` 机制完成四层彻底修复：
1. **1204 开局失地核心**：给 1204 尼西亚帝国（`BYZ`）补全 20 块第四次十字军前的核心失地（含君士坦丁堡、博斯普鲁斯海峡、赫勒斯滂海峡与色雷斯核心区）。
2. **月度 O(1) 自动整合兜底**：1204–1336 年间，只要 `BYZ`、`EPI`（伊庇鲁斯）或 `TRE`（特拉比松）收复君堡且整合度尚未达 `core`，月度检查立即将君堡及同省已拥有地块晋升为完整核心（`core`）。
3. **光复君堡决议同步核心化**：点击 `oe_wp45_dec_1204_restore_roman_constantinople` 时，立即核心化君堡、同省及色雷斯全部已拥有地块并迁都。
4. **《破碎紫袍》局势与事件同步**：局势复辟结局与 `oe_v47_1204.15` 选项同步授予完整 `core` 整合度。

### 5. 全模组零卡顿治理与引擎硬门禁升级（主模组 + 编年史，v51.0 & v55.0）

- **313 处重循环事件卡顿炸弹清零**：针对 `oe_elr.10` 等大型加 BUFF 事件悬停/弹出瞬间卡顿问题，对主模组（151 处）与编年史（162 处）全量审计重构，将重型 `every_owned_location` / `every_country` 循环收入 `hidden_effect` 并配以简洁清晰的 `custom_tooltip` 摘要，帧率与弹窗响应丝滑如常。
- **全量 735 项决议防暂停无限刷漏洞（`R69`）**：全面排查修复暂停状态重复点击套利漏洞，并写入永久 CI 门禁。
- **79 个自定义附庸外交分类文案全补齐（`R71`）**：彻底消除外交界面右侧自定义附庸分类键名裸露问题。
- **78/78 引擎硬门禁（`R01–R78`，156/156 自测通过）**：涵盖决议 `option`/分类、事件 `outcome`、局势互斥条件、纹章文件、跨 12 剧本自定义 TAG 休眠存根与 `province_definition:` 合法语法校验。

### 6. v51.0–v54.0 重大合并内容一览（全时代编年史 + 主模组）

- **v51.0 全时代开局基建与 492 项前置科技**：355 国 11 时代独立档案、111 个顶配强国继承人/内阁/AI 偏好、全 12 剧本按历史地理分层的思潮与 492 项 1337 前革新自动校准（非洲与美洲土著真实留白，殖民美洲自动跟进）。
- **v52.0 古典晚期（361–768）深度大修**：30 个历史子 TAG、3 类古典附庸（唐藩镇/萨珊军区总督/哈里发行省）、2 个古典国际组织、40 国常备军、丝路古典经济与 10 项古典 CB；532 三章案双轨局势；大厅可选古典 IF（苏瓦松西亚格里乌斯/亚瑟王、卑路斯三世唐波斯都督府与古吉拉特帕西）。
- **v53.0 大蒙古国五汗分封、第四罗马重构与 6 大可选 IF 宇宙**：
  - **1204–1368 大蒙古国五汗分封**：5 类蒙古附庸、12 个可分封子汗国（`M5A–M5L`）、25 条跨汗事件、开局孛儿帖/窝阔台/拖雷/失吉忽秃忽历史廷臣与蒙古省会闪击（含玩家防守豁免）。
  - **第四罗马全面重构**：斯巴达尼亚重做（8 格尤卡坦核心 + 独立市场 + 3,800 正规军 + 4 波 AI 征服）、第四罗马事件去重节奏化、亚非双洋扩张局势、12 座新世界奇观与 10 项时代内阁行动。
  - **6 大大厅可选架空 IF 宇宙**：澳宋、阿里不哥宗王海外分封、永乐郑和永航舰队、1307 圣殿骑士团大西洋流亡、1311 曼萨·阿布巴克尔二世新马里、1444 格拉纳达巴西流亡。
- **v54.0 近代早期（1648 & 1776）全球帝国大修**：1648 清朝三藩附庸（吴三桂/尚可喜/耿仲明/孔有德）、西班牙海外总督区、郑成功东宁与吕宋南洋海上大明 IF、58 国常备军；1776 北美大陆会议 IO、马拉地邦联 IO、东印度公司总督辖区、清朝理藩院盟旗与十全武功、奥斯曼帕夏省、55 国常备军；黄金海盗时代/拿骚、七年战争与格林尼治/冬宫/美泉宫/布达拉宫 4 大奇观。
- **v55.0 1821 与 1337 十一大经典国收官**：1821 德意志邦联与欧洲协调 IO、拿破仑墨西哥湾新大陆流亡 IF、61 国常备军；1337 十一大经典国（苏格兰、爱尔兰、北欧、波西米亚、匈牙利、埃塞俄比亚、马里、大越、满者伯夷、阿瑜陀耶、南北朝日本）深度内容补全。

### 7. 实机验收汇总（2026-11-27，EU5 1.4.9，`rc1–rc4` 四轮）

- **载入期清零验收（`rc1 → rc2 → rc4`）**：`rc1` 暴露的 525 条载入期报错与 6,113 行 `M5x` 休眠政体刷屏全部清零；`rc4` 同载音乐子模组发行版，`M5J` 撞色告警消失、音频/Bank 报错 `0`、载入期阻断报错 `0`。
- **532 汪达尔自动受降实测（`rc4`）**：以专属光复 CB 宣战汪达尔并推进至下月初，顺利弹出《帕普阿山受降：汪达尔王国覆灭》，科西嘉全部 8 城随北非一并划归东罗马（东罗马地块升至 602 格），汪达尔地块归零灭国，`province` 脚本报错 `0`。
- **人类防守方保护实测（`rc4`）**：AI 攻陷玩家地区首府埃迪尔内时仅划转埃迪尔内 1 格（602 → 601）并弹出警示事件，周围行省完好无损，日志纯净。
- **1204 尼西亚君堡核心实测（`rc4`）**：1204 `BYZ` 开局即持有君堡与埃迪尔内历史核心；直接收复即刻为核心；手动降级为 `conquered` 后推进至下月初，在点击事件选项前月度兜底已自动将君堡恢复为 `core`，全程 0 报错。
- **音乐子模组实机音频验收（`rc2 & rc4`）**：加载 0 报错，实机录音与声学指纹核验确认第 1 曲与第 47 曲《极乐原野》正常播音。
- **未逐项实机走完的部分**：12 个剧本的全部中后期事件链、6 大可选 IF 宇宙及 1337 十一国全部事件分支已通过 `78/78 R01–R78 --strict`、双语 125,463 词条严格检查与平衡性门禁验证，未逐一手动游玩至终局。

---

## 二、English Changelog

> **Status:** v55.0 release (EU5 1.4.9), combining all five milestones **v51.0–v55.0**. Candidates `v55.0-rc1` to `rc4` went through four rounds of live testing in EU5 1.4.9 on 2026-11-27; the released packages are the live-tested `rc4` with no further changes to mod script files (only `README.md` was updated).
> **Saves:** v55.0 is **not** compatible with older saves. Please start a new game.
> **NEW Companion Music Submod:** [Project Phoenix Soundtrack (`3846593343`)](https://steamcommunity.com/sharedfiles/filedetails/?id=3846593343) — 60 Roman symphonic & Mediterranean tracks (~148 min), loudness-matched into EU5's dynamic music system, keeping all vanilla tracks, multiplayer checksum-safe, runnable standalone or with the full Project Phoenix suite.

Made by: 寐夜空灵, miscos330

### 0. NEW Official Companion Submod: Project Phoenix Soundtrack (`3846593343`)

- **60 Roman & Mediterranean Symphonic Tracks (~148 min):** Loudness-matched and encoded in native EU5 1.4.9 Wwise format, integrated seamlessly into vanilla dynamic playlists (~40% mix alongside all vanilla tracks): 14 war pieces, 37 peace & imperial suite pieces, and 19 Byzantine court/chant tracks.
- **Checksum-Safe & Live-Verified:** All files live under `loading_screen/` (multiplayer checksum unchanged; "Dynamic - All" audio mode recommended). Live-verified in EU5 1.4.9 with 0 audio/bank errors and acoustic fingerprint playback verification.

### 1. 532 Justinian Reconquest Grand Redesign (Chronicles, v55.0)

- **3 Bespoke Reconquest CBs:** Belisarius (Africa), Belisarius/Narses (Italy), and Liberius (Spania) now wage theater-specific reconquest wars (`cb_oe_v55_532_vandalic_reconquest` / `gothic_reconquest` / `spania_reconquest`).
- **Warscore + Key-City Automatic Capitulation & 10-Year Truces:**
  - Africa (Carthage + ≥55% warscore) triggers *Surrender at Mount Papua*, transferring North Africa, Sardinia, Corsica (all 8 tiles), and the Balearics and eliminating the Vandal Kingdom.
  - Italy (Rome + Ravenna + ≥60%) triggers Ostrogothic surrender; Spania (Córdoba + Seville + Cartagena + ≥45%) cedes southern Spania.
  - Surviving defeated realms automatically receive a 10-year truce with East Rome and the theater recipient.
- **True Ostrogothic Kingdom (`FXO`) & Strict Causal Event Gating:** Replaces the anachronistic Kingdom of Italy with the historical Ostrogothic Kingdom and strictly gates Totila's revival, Ravenna crown, and postwar events behind actual battlefield progress.

### 2. All-11-Era Historical Religion Overhaul (Chronicles, v55.0)

Eliminates anachronistic pre-1054 Catholicism, Cathar placeholders, and misassigned East European Romuva by introducing **9 complete historical religions**:
- **Chalcedonian Christianity (`oe_rel_chalcedonian`):** Unified pre-1054 East-West Church across 361–768, with a dynamic **1054 Great Schism** chain (historical split or imperial reconciliation).
- **Arianism (`oe_rel_arianism`):** Authentic 361–532 Ostrogothic, Visigothic, Vandal, Burgundian, Gepid, and Lombard elites ruling over Chalcedonian Roman subjects.
- **Insular Christianity (`oe_rel_insular`)** (+ 664 Synod of Whitby), **Donatism (`oe_rel_donatism`)**, **Iconoclasm (`oe_rel_iconoclasm`)** (+ 787 Second Council of Nicaea), **Slavic Paganism (`oe_rel_slavic_pagan`)**, **Celtic Druidism (`oe_rel_celtic_pagan`)**, **Continental Germanic Paganism (`oe_rel_germanic_pagan`)**, and **Pre-Islamic Arab Paganism (`oe_rel_arab_pagan`)**.

### 3. All-Era & 1337 Dynamic Province-Capital War & Auto-Victory Engine (Main + Chronicles, v55.0)

- **Lobby Game Rule (`oe_v55_gr_dynamic_province_seizure`):** Default ON (*Province-Capital Seizure + Auto-Capitulation*), switchable to *Single-Tile Seizure* or *Vanilla Peace*.
- **Province-Capital Whole-Province Seizure:** Capturing an enemy provincial capital in expedition wars, historical decisive CBs, 1337 major wars (14 Main Mod CBs, 9 Byzantine campaign zones, 5 vanilla situations, or the "Proclaim War of Subjugation" decision) immediately transfers all enemy locations in that province while strictly protecting allies, neutrals, and civil wars.
- **Human-Defender Protection:** When an AI captures a human player's provincial capital, ONLY that single capital tile flips (never the whole province) and a warning alert fires.
- **Warscore + Capital Auto-Victory:** Holding an AI enemy's capital at ≥65% warscore (or ≥80% overall) offers a 3-way surrender choice (full theater/annexation, vassalization, or decline for normal peace); human defenders are never forced to capitulate.

### 4. 1204 Nicaea / Epirus / Trebizond 4-Layer Constantinople Core Restoration (Chronicles, v55.0)

Fixes the community-reported 1204 Nicaea Constantinople core issue using vanilla EU5 1.4.9 `add_core` + `change_integration_level = core`:
1. 20 historical pre-1204 lost cores (`our_cores_conquered_by_others`, including Constantinople and core Thrace) at start for 1204 `BYZ` (Nicaea).
2. O(1) monthly integration safeguard for `BYZ`/`EPI`/`TRE` (`1204–1336`) automatically restoring full `core` integration on Constantinople and owned tiles in its province.
3. `oe_wp45_dec_1204_restore_roman_constantinople` promotes Constantinople, its province, and owned `thrace_area` tiles to `core`.
4. *Shattered Purple* restoration endings and `oe_v47_1204.15` updated in sync.

### 5. Zero-Lag Buff Event Audit & 78/78 Engine CI (Main + Chronicles, v51.0 & v55.0)

- **313 Heavy-Loop Event Lag Bombs Cleared (`R70`):** Refactored `oe_elr.10` and 312 other heavy buff/effect loops (151 Main Mod + 162 Chronicles) into `hidden_effect` with clean `custom_tooltip` summaries, eliminating hover/popup frame drops.
- **735 Decisions Anti-Exploit Audit (`R69`)** + **79 Custom Subject Diplomacy Categories Localized (`R71`)** + **78/78 Strict Engine Rules (`R01–R78`, 156/156 selftests PASS)**.

### 6. Merged v51.0–v54.0 & 1821/1337 Highlights

- **v51.0:** 355 all-era country profiles across 11 starts, 111 flagship power cabinets/heirs/AI stances, historically stratified institutions & 492 pre-1337 advances.
- **v52.0:** 30 Late Antique sub-TAGs, 3 classical subject archetypes, 2 classical IOs, 40 standing armies, 10 classical CBs, 532 Three Chapters Schism, and Classical opt-in IFs (Syagrius/Arthur & Peroz III Tang Persian Protectorate/Parsi Gujarat).
- **v53.0:** **1204–1368 Great Mongol Empire Five-Khan Enfeoffment** (5 subject types, 12 sub-khanates `M5A–M5L`, 25 cross-khan events, historical 1204 court, Mongol Blitzkrieg); rebuilt **Fourth Rome** (overhauled Spartania, paced events, Asia-Africa expansion, 12 new wonders, 10 cabinet actions); **6 Opt-In IF Universes** (Austral-Song, Ariq Böke Overseas, Eternal Zheng He, 1307 Templars, 1311 Mansa Abu Bakr II New Mali, 1444 Granada Brazil).
- **v54.0:** 1648 Qing Three Feudatories, Spanish Viceroyalties, Koxinga Nanyang IF, 58 standing armies; 1776 Continental Congress IO, Maratha Confederacy IO, EIC, Qing Lifanyuan, Ottoman Pashaliks, 55 standing armies; Golden Age of Piracy/Nassau, Seven Years' War, 4 Enlightenment wonders.
- **v55.0:** 1821 German Confederation & Concert of Europe IOs, Napoleon Gulf of Mexico IF, 61 standing armies; 1337 deep polish for 11 iconic nations (Scotland, Ireland, Scandinavia, Bohemia, Hungary, Ethiopia, Mali, Dai Viet, Majapahit, Ayutthaya, Nanboku-chō Japan).

### 7. Live Verification Summary (2026-11-27, EU5 1.4.9, `rc1–rc4`)

- **Load-Time Closure (`rc1 → rc2 → rc4`):** All 525 `rc1` load errors and 6,113 lines/session of `M5x` dormant government spam resolved to `0`; `rc4` loaded cleanly alongside the OST release build (`M5J` color warning gone, `0` audio/bank errors, `0` blocking load errors).
- **532 Vandalic Auto-Capitulation (`rc4`):** *Surrender at Mount Papua* fired cleanly, 0 `province` errors, all 8 Corsica tiles transferred with Africa (East Rome 602 locations), Vandals eliminated (`num_locations = 0`).
- **Human-Defender Protection (`rc4`):** AI capturing player provincial capital Edirne flipped ONLY Edirne (602 → 601) and triggered the warning event; clean log.
- **1204 Nicaea Constantinople Core (`rc4`):** Setup cores verified on Constantinople & Edirne; recapture granted `core` immediately; downgrading to `conquered` proved the monthly pulse automatically restores `core` within one month before picking any event option (0 errors).
- **OST Audio (`rc2 & rc4`):** Verified 0 load errors plus live playback acoustic fingerprint match (tracks #1 & #47).
- **Not individually played end-to-end:** Full late-game chains across all 12 starts, all 6 opt-in IF universes, and all 11-nation 1337 branches were validated by `78/78 R01–R78 --strict` CI, 125,463-key EN/ZH strict localization checks, and balance checks rather than played manually to 1836.

---

# 《凤凰计划（OEBYZ）》v50.0 更新日志

> **发布状态**：v50.0 正式版（EU5 1.4.9），合并 v49–v50 的全部更新。候选版 v50.0-rc1 到 rc4 于 2026-11-26 至 27 在 EU5 1.4.9 上经过四轮实机验收；发布包就是实测通过的 rc4，没有再改模组文件（只更新了 README）。
> **存档提示**：v50.0 **不兼容旧版本存档**，请新开一局。
> **新封面**：主模组换了新的封面图和启动器缩略图。

制作：寐夜空灵、miscos330

---

## 一、中文更新日志

### 1. 征服者远征与历史决战（全时代编年史）

- **532 查士丁尼光复重做**：
  - 贝利撒留北非远征军、贝利撒留与纳尔塞斯意大利远征军、利贝里乌斯西班牙远征军，都改成可独立作战的远征军附庸。
  - 发动时先选目标国，再选沿海登陆点；在战区内占领即征服，被敌人夺回就失守。
  - 远征军有增援、召回、册封总督区、吞并四种互动。
  - 新增 540 年拉文纳哥特王冠事件（可切换扮演贝利撒留）、托提拉复起，以及西方诸王国联合并致信库思老一世造成的两线压力；伊苏里亚、奥斯若伊奈等内部边区可以和平整合。
  - 宣战只针对目标国及其附庸，不再牵连整个马格里布。
- **其余各时代的远征：**
  - 361 尤里安两河远征；
  - 395 斯提里科与阿拉里克；
  - 476 狄奥多里克征意大利；
  - 632 哈立德与大唐李靖；
  - 768 查理曼伦巴第远征；
  - 1204 光复君士坦丁堡先锋与蒙古万户；
  - 1453 教宗援军与乌尔班巨炮；
  - 1648 郑成功北伐；
  - 1776 叶卡捷琳娜“希腊计划”远征军；
  - 1821 拿破仑归来（可切换扮演拿破仑）。
- **帝国收复失地宣战理由与 16 套决战和约**：1337 以外的开局都有通用的帝国收复失地宣战理由，另有 16 套一对一的历史决战宣战理由和专属和约，配 19 张羊皮纸图标。

### 2. 科技、开局与经济（全时代编年史）

- **科技树：**1337 之前的 5 个时代新增 54 项基础革新，包括征税、稳定投入、农耕、采矿、城建修路、舰船和基础法典。古典晚期和中世纪前期开局不再无法征税或建造。
- **开局科技：**1337 以外的 11 个开局按年代解锁初始科技，1776 和 1821 开局的科技断层大幅减少。
- **附庸与特权：**
  - 1337 之前的时代都能有附庸，532 东罗马开局的 8 个边区与同盟蛮族附庸不再首日解体。
  - 361–1453 的拜占庭开局配齐专属特权，532 从 0 项增加到 15 项。
- **开局校准：**
  - 古典晚期人口不再成倍下滑；
  - 删掉不合时代的建筑和过多的城堡；
  - 校准各开局的军队、舰队和国库；
  - 361 罗马开局由赤字改为盈余：rc3 实测每月 −78，v50.0 为 +124.75。

### 3. 第四罗马（全时代编年史）

- **美洲土著：**1444/1453 的美洲新增 54 个历史土著国家，配原住民政策法令和 18 条事件。
- **衍生国家：**加强 14 个衍生国家、文兰与帝国附庸；斯巴达尼亚有四阶段西进玩法和专属霸权宣战理由。
- **总督区：**新建总督区时优先把已有的分支国家就地升格，避免同一地区出现重复总督区。总督区增加到 17 个，其中 7 个在旧大陆。新增三种分封方式和 24 条重返欧洲事件。
- **造船价格：**修好时代数增加后船价翻倍的问题，不会再出现约 6,400 金的轻型战舰。
- **新大陆城镇：**新增新大陆建镇和建城决议，以及东地中海希腊难民潮。
- **1444 继承：**约翰八世补上父母，继承人正确识别为君士坦丁十一世，驾崩后直接继位，不进入摄政。西渡建立极乐洲新罗马时，同王朝成员一起随行。

### 4. 罗马—希腊多神教

- **主模组：**新增 6 位神祇、30 项大祭司神谕、4 项宗教特质、2 项内阁行动、3 项决议和 23 条事件。
- **编年史第四罗马：**新增新大陆 6 座古典神庙奇观、“诸神和平”体系和 12 条跨洋宗教事件。

### 5. v49 合入内容、美术与性能

- **v49.0：**26 座三阶世界奇观；传奇雇佣兵团、海盗与大师；各时代君主服饰肖像；古典奥林匹克与无敌舰队；游戏规则集中设置。
- **v49.5：**
  - 新增 395 东西罗马双紫局势，退役 21 个重复的旧局势；
  - 补充女性君主肖像；
  - 为 123 项改革和特权加上地理、科技、宗教条件，例如没到太平洋就不能选太平洋相关的特许。
- **美术：**重绘约 366 张油画风格的界面卡片（阶层特权、政府改革、法律、附庸、国际组织纹章、建筑、内阁、局势、灾难），另有 34 张古典时代徽章与横幅、12 个古典机构图标。1337 的“军区制”改革卡重新绘制。
- **性能与兼容：**优化 103 条定期脚本，改善中后期卡顿；编年史改了两个标签（`RMN→RMY`、`ARC→CTK`），与《国家命运》不再冲突。

### 6. 实机问题修复（rc1–rc4 四轮实机验收）

- 532 发动远征不再刷出大量报错，也不再让整个马格里布对远征军宣战；“托提拉复起”的逻辑正常载入；局势面板不再新旧两套按钮并存。
- 神圣罗马帝国相关行动、特权和法律在没有该组织或国家的年代不再报错。
- 361 革新不再开局全部研究完成，现在显示“25/109”，并有可研究项目。
- 1337 等开局的自建文化不再提示“没有人口”。
- 补齐 8 个远征附庸类型的本地化和 16 条国家互动消息类型；开局生成人物时文化、宗教不再为空。
- 1204 行动脚本的 `'root'` 比较报错归零；古典晚期 3 项革新的语法错误修好。
- 主模组启动器缩略图换成新封面。

### 7. 实机验收（2026-11-26 至 27，EU5 1.4.9）

- **532 东罗马：**
  - 开局月结余 +311，有 15 项特权和 8 个附庸；
  - 发动北非远征（目标汪达尔，加贝斯登陆），只有 4 场相关战争，远征脚本报错为 0。
- **1444 拜占庭：**
  - 造船价格正常；
  - 继承人是君士坦丁十一世，约翰八世驾崩后直接继位；
  - 西渡建立极乐洲新罗马后，国王驾崩同样正常继位，皇弟随行。
- **361 罗马：**月结余 +124.75，革新可研究。
- **1337 拜占庭：**“军区制”卡片显示新油画，载入时没有“文化无人口”提示。
- **1204：**观察模式运行 6 年，没有刷屏报错。
- **其余开局：**395、476、632、768、1648、1776、1821 都能正常进局，并在观察模式下运行 1 到 4 年，没有刷屏报错。
- **没有实测：**
  - 540 拉文纳事件和 532 战后转总督区；
  - 361、1648、1821 由玩家亲自发动的远征；
  - 26 座奇观和多神教神谕的逐项操作。

### 8. 已知问题

- 1444 拜占庭开局，王室改革显示“7/6”，超出上限。
- 1204 运行中原版威尼斯事件（`flavor_ver.txt`）会持续报“人物作用域为空”，不影响游玩。
- 361 罗马的教士税是 0（教士人口少、教堂维护多，属于阶层收支的正常结果）。

---

## 二、English Changelog

> **Status:** v50.0 release (EU5 1.4.9), covering everything in v49 and v50. Candidates v50.0-rc1 to rc4 went through four rounds of live testing in EU5 1.4.9 on 2026-11-26/27; the released packages are the tested rc4 with no further changes to mod files (only the README was updated).
> **Saves:** v50.0 is **not** compatible with older saves. Please start a new game.
> **New cover:** the main mod has a new cover image and launcher thumbnail.

Made by: 寐夜空灵, miscos330

### 1. Conqueror expeditions and decisive wars (Chronicles of All Eras)

- **532 Justinian's reconquest reworked:**
  - Belisarius in Africa, Belisarius and Narses in Italy, and Liberius in Spain are now expeditionary subjects that fight on their own.
  - You pick a target country and a coastal landing site. Locations occupied inside the theatre are conquered at once, and lost again if the enemy retakes them.
  - Each expedition can be reinforced, recalled, chartered as an exarchate or annexed.
  - New: the 540 Ravenna Gothic crown event (you can switch to playing Belisarius), Totila's revival, and Western kings rallying and writing to Khosrow I for a two-front squeeze. Inner marches such as Isauria and Osroene can be integrated peacefully.
  - Wars are now declared only on the target and its subjects, not on the whole Maghreb.
- **Expeditions in the other eras:**
  - 361 Julian's Mesopotamian campaign;
  - 395 Stilicho and Alaric;
  - 476 Theoderic in Italy;
  - 632 Khalid and the Tang general Li Jing;
  - 768 Charlemagne in Lombardy;
  - 1204 the Constantinople reconquest vanguard and the Mongol tumens;
  - 1453 papal relief and Urban's great gun;
  - 1648 Koxinga's northern campaign;
  - 1776 Catherine's Greek Plan army;
  - 1821 Napoleon's return (you can switch to playing Napoleon).
- **Imperial reconquest and 16 decisive peace treaties:** every start except 1337 gets a general imperial reconquest casus belli, plus 16 paired historical casus belli with their own peace treaties and 19 parchment icons.

### 2. Technology, starts and economy (Chronicles of All Eras)

- **Technology:** 54 basic advances for the five ages before 1337: taxation, stability investment, farming, mining, building and roads, ships and early laws. Late Antique and early medieval starts can tax and build again.
- **Starting technology:** the 11 starts other than 1337 unlock their starting technology by year, which greatly reduces the gaps in 1776 and 1821.
- **Subjects and privileges:**
  - Subjects are allowed in all ages before 1337, and the 8 frontier and foederati subjects of 532 East Rome no longer break away on day one.
  - The Byzantine starts from 361 to 1453 get their Byzantine privileges; 532 goes from 0 to 15.
- **Start calibration:**
  - The doubled Late Antique population decline is gone;
  - anachronistic buildings and surplus forts are removed;
  - armies, fleets and treasuries are calibrated in every start;
  - 361 Rome now starts with a surplus: −78 a month in the rc3 test, +124.75 in v50.0.

### 3. Fourth Rome (Chronicles of All Eras)

- **Native Americans:** 54 historical native countries in the Americas of 1444/1453, with a native policy law and 18 events.
- **Successor states:** the 14 successor states, Vinland and the imperial subjects are stronger; Spartania gets a four-stage westward campaign and its own hegemony casus belli.
- **Exarchates:** new exarchates are made by promoting an existing branch realm where possible, so the same region no longer gets two. There are now 17 exarchates, 7 of them in the Old World, three ways of enfeoffment and 24 return-to-Europe events.
- **Ship prices:** the per-age doubling is fixed, so light warships no longer cost about 6,400 gold.
- **New World towns:** new decisions to found towns and cities in the New World, and an eastern Mediterranean Greek refugee wave.
- **1444 succession:** John VIII now has his parents set, so Constantine XI is recognised as heir and succeeds directly when John dies, without a regency. When the court sails west to found the Elysian New Rome, the rest of the dynasty goes too.

### 4. Roman–Hellenic polytheism

- **Main mod:** 6 new deities, 30 high-priest omens, 4 religious aspects, 2 cabinet actions, 3 decisions and 23 events.
- **Chronicles Fourth Rome:** 6 classical temple wonders in the New World, a *Pax Deorum* system and 12 transatlantic religious events.

### 5. Merged v49 content, art and performance

- **v49.0:** 26 three-tier world wonders; legendary mercenary companies, pirates and masters; period ruler portraits; the classical Olympics and the Armada; a central game-rules screen.
- **v49.5:**
  - A 395 situation for the two Roman courts; 21 duplicate old situations retired.
  - More portraits for female rulers.
  - Geographic, technology and religious conditions for 123 reforms and privileges; for example, Pacific charters need a Pacific coast.
- **Art:** about 366 interface cards redrawn as oil paintings (estate privileges, government reforms, laws, subjects, international organisation crests, buildings, cabinet, situations, disasters), plus 34 classical age emblems and banners and 12 classical institution icons. The 1337 "Theme System" reform card is redrawn.
- **Performance and compatibility:** 103 recurring scripts optimised to reduce late-game slowdown; two Chronicles tags renamed (`RMN→RMY`, `ARC→CTK`) so they no longer clash with National Destinies.

### 6. Fixes from live testing (four rounds, rc1–rc4)

- In 532, launching an expedition no longer floods the error log or brings the whole Maghreb into the war; Totila's revival loads; the situation panel no longer shows old and new buttons side by side.
- Holy Roman Empire actions, privileges and laws no longer raise errors in eras without that organisation or country.
- 361 no longer starts with all advances researched; it shows "25/109" with advances available.
- Custom cultures no longer report "no pops" in 1337 and other starts.
- Localisation for 8 expedition subject types and 16 country-interaction message types added; characters created at game start no longer get an empty culture or religion.
- The 1204 action `'root'` comparison errors are gone, and a syntax error in 3 Late Antique advances is fixed.
- The main mod's launcher thumbnail now shows the new cover.

### 7. Live test (2026-11-26/27, EU5 1.4.9)

- **532 East Rome:**
  - +311 a month at the start, with 15 privileges and 8 subjects.
  - The Africa expedition (target the Vandals, landing at Gabès) led to 4 related wars, with 0 expedition script errors.
- **1444 Byzantium:**
  - Ship prices are normal.
  - Constantine XI is heir and succeeds directly when John VIII dies.
  - After sailing west to the Elysian New Rome, succession works the same way and the emperor's brothers go along.
- **361 Rome:** +124.75 a month, with advances available.
- **1337 Byzantium:** the "Theme System" card shows the new painting; no "culture has no pops" messages at load.
- **1204:** six years in observer mode without error floods.
- **Other starts:** 395, 476, 632, 768, 1648, 1776 and 1821 all start and ran 1 to 4 years in observer mode without error floods.
- **Not tested:**
  - the 540 Ravenna event and turning the 532 expeditions into exarchates after the war;
  - player-launched expeditions in 361, 1648 and 1821;
  - the 26 wonders and the polytheist omens one by one.

### 8. Known issues

- In a 1444 Byzantine game, the crown reforms show "7/6", over the limit.
- In 1204, the vanilla Venetian event (`flavor_ver.txt`) keeps logging an empty character scope; this does not affect play.
- 361 Rome's clergy tax is 0: there are few clergy and many churches to maintain, so this is the normal estate budget, not a bug.

---

# 《凤凰计划（OEBYZ）》v48.0 更新日志

> **发布状态**：v48.0 正式版（EU5 1.4.9），合并 v41–v48 的全部更新。候选版 v48.0-rc2 已于 2026-11-26 在 EU5 1.4.9 实机验收；发布包在 rc2 基础上修了 3 处小问题（见第 5 节），修后在 1648 开局再次实机复测。
> **存档提示**：v48.0 **不兼容旧版本存档**，请新开一局。
> **雄鹰陨落**：已并入《全时代编年史》（3844848618）。旧的《雄鹰陨落 361–768》条目（3845632550）停止更新，请取消订阅，不要与 v48.0 同时启用。

制作：寐夜空灵、miscos330

---

## 一、中文更新日志

### 1. 全时代编年史（3844848618，原《全时代历史剧本拓展包》）

- **十二个开局合一**：《雄鹰陨落 361–768》并入，现有 361 / 395 / 476 / 532 / 632 / 768 / 1204 / 1337 / 1444 / 1648 / 1776 / 1821 共 12 个开局，书签界面顶部可切换“古典晚期”与“中世至近世”两栏。可独立运行。
- **近世局势（v48）**：
  - 1648：南明中兴（郑成功北伐与康熙平藩）、英荷海洋争霸与克伦威尔革命、路易十四与凡尔赛。
  - 1776：大西洋帝国联邦与美国独立战争、1793 乾隆十字路口（马戛尔尼使团）、叶卡捷琳娜“希腊计划”。
  - 1821：希腊起义与“伟大理想”、穆罕默德·阿里与道光自强，以及玩家可选的彩蛋“圣赫勒拿密信”（可选纯史实关闭）。
- **1204 与欧亚架空线（v47）**：《破碎的紫衣》七方局势、开禧北伐与宋金蒙；大明重启下西洋（含海外附庸“西洋市舶宣慰司”，可与第四罗马在太平洋会师）、瓦尔纳大捷、双鹰合璧、安达卢斯复兴、马穆鲁克重开苏伊士、撒马尔罕科学黄金时代。AI 默认走史实路线。
- **古典晚期旗舰局势（v43–v46）**：361 尤里安太阳神复兴、476 西罗马最后火种、532 查士丁尼与五大牧首区、632 大唐天可汗国际组织与安西都护府、768 三帝纪元（含 802 查理曼与伊琳娜联姻）。
- **第四罗马（v44）**：帝国威权控制台（三个分页、按权威解锁的行动）、6 种附庸与 10 项附庸互动、登陆后的流亡与衍生国家。
- **国家与文化介绍（v48）**：约 210 条双语介绍重写，覆盖第四罗马、古典晚期帝国、1204–1821 补缺国家与编年史自建文化。

### 2. 主模组（3667460405）

- **跨时代隔离**：主模组的 14 世纪事件、局势与开局钩子加上年代下限，古典晚期开局不再弹出奥斯曼命运、新的朝贡国等内容。
- **罗马化改革**：AI 控制的希腊语、东正教拜占庭与第四罗马不再主动拉丁化（玩家仍可自行选择）。
- **报错与文字修复**：时代名叠字、战争名显示原始键、本地化键哈希冲突、重复定义的脚本键、`has_controller` 等载入报错全部清零。

### 3. 其他子模组

- **国家命运深度整合**（3845632867）、**兼容桥**（3845632818）、**Glorp UI 凤凰适配**（3845632981）、**地图美化 A/B/C**（3845632643 / 3845632683 / 3845632746）：随主模组同步到 v48.0。

### 4. 实机问题修复（v46–v48 两轮实机验收）

- 古典晚期开局不再弹出 14 世纪事件；768 三帝局势的地图配色不再刷屏报错。
- 开局首月不再废除元老院或枢密院；`invalid government type` 清零。
- AI 第四罗马登陆后宫廷语言与礼拜语言保持希腊语，宗教为正统大公教会。
- 1444 郑和重航触发器的作用域错误修好（rc1 时 1444 开局 3 分钟约 11.4 万条报错，现为 0）。
- 361 战争名正常显示国名；本地化键哈希碰撞为 0；附庸互动的消息类型补齐。
- 532 东亚战区插图、361/768 事件配图、1648 白银事件配图换成油画；632 安西四镇开局计数为 0/4。

### 5. 发布前追加修复（rc2 之后）

- 1648：两个被南明中兴取代的旧明清局势不再同时启动。
- 1648：南明中兴局势换用清军入城的油画，不再与 1444 郑和局势同图。
- 1444：“滇云六十七土司勘合录”与“乐山大佛护持令”两个事件换了更贴切的配图（后者原先是藏地宫殿）。

### 6. 实机验收（2026-11-26，EU5 1.4.9）

- 1444 大明：郑和开场事件 1445.1 弹出，局势激活，面板行动可用；运行约一年，`has_culture_group` 报错为 0。
- 1648 南明：局势面板正常，运行约一年，无刷屏报错；修复版再测，横幅只剩南明中兴与英荷海洋争霸。
- 361 罗马：战争名正常，不再出现 14 世纪事件。
- 632 大唐、768 法兰克、1451 第四罗马帝国威权面板：在 rc1 轮测试正常。
- 本轮没有实测：1204、1776、1821 的新局势面板；第四罗马国家的悬停介绍；1648 大厅里墨西哥的国名。

### 7. 已知问题

- 1444 载入日志里仍有 16 条自建文化“没有人口”的提示（不影响游玩）。
- 部分东亚事件之间共用同一张配图。

---

## 二、English Changelog

> **Status:** v48.0 release (EU5 1.4.9), covering everything from v41 to v48. The v48.0-rc2 candidate was tested in EU5 1.4.9 on 2026-11-26; the released package adds 3 small fixes on top of rc2 (section 5), which were tested again in a 1648 game.
> **Saves:** v48.0 is **not** compatible with older saves. Please start a new game.
> **The Fallen Eagle:** now part of Chronicles of All Eras (3844848618). The old "The Fallen Eagle 361–768" item (3845632550) is no longer updated; please unsubscribe and do not enable it with v48.0.

Made by: 寐夜空灵, miscos330

### 1. Chronicles of All Eras (3844848618, formerly All-Eras Historical Bookmarks)

- **Twelve starts in one:** The Fallen Eagle 361–768 is merged in, giving 12 starts (361 / 395 / 476 / 532 / 632 / 768 / 1204 / 1337 / 1444 / 1648 / 1776 / 1821); the bar at the top of the bookmark screen switches between Late Antiquity and Medieval to Early Modern. Runs standalone.
- **Early-modern situations (v48):**
  - 1648: the Southern Ming revival (Koxinga's northern campaign and the Revolt of the Three Feudatories), the Anglo-Dutch sea wars and Cromwell, Louis XIV and Versailles.
  - 1776: an Atlantic imperial federation and the American War of Independence, the 1793 Qianlong crossroads (the Macartney embassy), Catherine's Greek Plan.
  - 1821: the Greek uprising and the Megali Idea, Muhammad Ali and Qing self-strengthening, and the optional "Letter from St Helena" easter egg (can be closed for a purely historical game).
- **1204 and Eurasian alternate histories (v47):** the seven-way Shattered Purple situation and the Kaixi Northern Expedition with Song, Jin and Mongols; the Ming treasure fleets sail again (with the overseas "Western Ocean Maritime Commission" subject, and a possible Pacific meeting with the Fourth Rome), Varna won, the double-headed eagles united, al-Andalus restored, a Mamluk Suez canal and Samarkand's golden age of science. The AI keeps to history by default.
- **Late Antiquity flagship situations (v43–v46):** Julian's solar revival in 361, the last flame of the West in 476, Justinian and the five patriarchates in 532, the Tang Heavenly Khagan organisation and the Anxi Protectorate in 632, the age of three emperors in 768 (including the 802 Charlemagne–Irene marriage).
- **Fourth Rome (v44):** an imperial authority console (three tabs, actions unlocked by authority), 6 subject types with 10 subject interactions, exile waves and successor states after the landfall.
- **Country and culture descriptions (v48):** about 210 bilingual descriptions rewritten, covering the Fourth Rome, the Late Antique empires, missing 1204–1821 realms and the Chronicles' own cultures.

### 2. Main mod (3667460405)

- **Era isolation:** the main mod's 14th-century events, situations and start hooks now have a lower year bound, so Late Antique starts no longer get Ottoman destiny, new tributaries and the like.
- **Romanisation reforms:** an AI-run Greek-speaking Orthodox Byzantium or Fourth Rome no longer latinises on its own (players still can).
- **Error and text fixes:** doubled age names, raw-key war names, localisation key hash collisions, duplicated script keys and `has_controller` load errors all cleared.

### 3. Other submods

- **National Destinies integration** (3845632867), **compatibility bridge** (3845632818), **Glorp UI Phoenix edition** (3845632981) and **Map beautification A/B/C** (3845632643 / 3845632683 / 3845632746): updated to v48.0 with the main mod.

### 4. Fixes from live testing (two rounds, v46–v48)

- Late Antique starts no longer fire 14th-century events; the 768 three-emperors map colours no longer flood the error log.
- The Senate or privy council is no longer abolished in the first month; `invalid government type` is gone.
- An AI Fourth Rome keeps Greek as court and liturgical language and Orthodoxy after landfall.
- The 1444 Zheng He trigger scope error is fixed (rc1 logged about 114,000 errors in 3 minutes of a 1444 game; now 0).
- War names in 361 show the country names; zero localisation key hash collisions; the subject interaction message types are complete.
- New oil paintings for the 532 East Asia theater, the 361/768 events and the 1648 silver event; the 632 Anxi Four Garrisons counter starts at 0/4.

### 5. Fixes added before release (after rc2)

- 1648: the two old Ming–Qing situations superseded by the Southern Ming no longer start alongside it.
- 1648: the Southern Ming situation uses a painting of Qing cavalry storming a Ming city instead of sharing the 1444 Zheng He picture.
- 1444: the Yunnan tusi register and Leshan Giant Buddha events get fitting pictures (the latter showed a Tibetan palace).

### 6. Live test (2026-11-26, EU5 1.4.9)

- 1444 Ming: the Zheng He opening event fired in 1445.1, the situation started and its panel actions work; about a year of play with 0 `has_culture_group` errors.
- 1648 Southern Ming: the situation panel works, about a year of play without error floods; in the fixed build only the Southern Ming and Anglo-Dutch situations are shown.
- 361 Rome: war names correct, no 14th-century events.
- 632 Tang, 768 Francia and the 1451 Fourth Rome imperial authority panel: worked in the rc1 round.
- Not tested this round: the new 1204, 1776 and 1821 situation panels; the Fourth Rome country tooltips; the name of Mexico in the 1648 lobby.

### 7. Known issues

- The 1444 load log still lists 16 custom cultures "with no pops" (no effect on play).
- Some East Asian events share the same picture.

---

# 《凤凰计划（OEBYZ）》v40.0 更新日志

> **发布状态**：v40.0 正式版（EU5 1.4.9），合并 v31–v40 的全部更新。候选版 v40.0-rc1 已于 2026-11-26 在 EU5 1.4.9 实机验收，发布包与验收时的文件逐字节一致。
> **存档提示**：v40.0 **不兼容旧版本存档**，请新开一局。
> **第四罗马**：已并入《全时代历史剧本拓展包》（3844848618）。旧的《1453 第四罗马》条目（3845210560）停止更新，请取消订阅，不要与 v40.0 同时启用。

制作：寐夜空灵、miscos330

---

## 一、中文更新日志

### 1. 主模组（3667460405）

- **凤凰指挥坞**：不覆盖原版界面的悬浮面板，v40.0 扩为 5 个页签，集中放置帝国敕令、批量御藩敕令、军事教范总动员和新增的“寰宇指引”，共 26 个按钮，实时显示状态。
- **拜占庭核心制度**：新增核心制度、28 项帝国大工程与配套危机；军区收归与军事教范（v31、v36）。
- **六大强权玩法**：奥斯曼（耶尼切里）、波斯（奇兹尔巴什与古拉姆）、罗斯（哥萨克与缙绅会议）、印度（曼萨布达尔与万教和谐）各分三个阶段演进；新增法兰西（三级会议与太阳王集权）、西班牙（卡斯蒂利亚黄金世纪与波旁改革）两条强权线；英国 53 项任务、东印度公司与明朝书院（v31、v39、v40）。
- **殖民地**：4 项殖民地自治与独立决议及多分支事件；30 套动态殖民地纹章旗；修正“新西班牙总督区总督区”之类的叠词国名（v38、v39）。
- **议和与停战**：罗马世界的仲裁决议改为只能由罗马领袖发起，仲裁范围限于帝国附庸之间，拜占庭不会再被强加与十几个邻国的停战；删除 26 条冗余议和条款（其中两条会把敌意显示成 -4.00）（v38）。
- **AI**：按年代调整 AI 性格与扩张方向。清朝不再被当作“欧亚均势调停者”，也不再沿用明朝的南洋殖民方向；原版“探索非洲海岸”不再出现在 1415 年以前、东亚、内亚和内陆国家；AI 不再在和平期反复缔结 5 年停战（v40）。
- **叙事**：345 篇事件重写，加入冷却，避免连续弹窗；45 条按年代与文化切换的国家简介，1648 的清朝、江户日本等不再显示 1337 年的简介（v38、v40）。
- **界面文字**：玩家可见文字中的内部代号全部清除。

### 2. 全时代历史剧本拓展包（3844848618）

- **六个纪元**：1204 / 1337 / 1444 / 1648 / 1776 / 1821，32 个战区、160 位推荐君主。
- **1444.11.11 瓦尔纳次日**：十五世纪开局从 1453 改为 1444.11.11。拜占庭约翰八世开局即可二选一：坚守君士坦丁堡反攻，或西渡大西洋建立第四罗马（原《1453 第四罗马》的全部内容已并入，含 5 座 3D 奇观与专属局势）。拜占庭由 AI 控制时，航程每 6 个月自动推进直到登陆（v39、v40）。
- **1821 新纪元**：希腊独立战争与维也纳体系，30 邦德意志邦联，大西洋与美洲战区（v35–v39）。
- **书签插图**：32 张战区插图全部按年代与地区重绘，不再出现年代错位的画面（v39、v40）。
- **历史校准**：各纪元补齐成年史实君主、修正跨洲国家标签、1648 美洲殖民地宗教人口、1821 各国国教与首都；1648 明清战争延续到清军南下，清朝首都显示“北京”，朝鲜显示“朝鲜王国”（v37–v40）。
- **玩法**：10 套时代局势（每套有独立面板）、17 项时代决议（含文化融合）、24 座世界奇观、1,400 余位成年史实人物（v39、v40）。

### 3. 雄鹰陨落 361–768（3845632550，独立运行）

- 24 张古羊皮纸战区地图与时代横幅，39 面推荐国家旗帜重绘（v37）。
- 16 种晚期古典与罗马行省文化；1054 年大分裂前的教会改用当时的名称，可选阿里乌派与希腊多神教；国名、尊号与发展度按史实调整（v38）。
- 10 套晚期古典局势、16 项决议（含 6 项文化融合）、18 座奇观（v39、v40）。
- 神圣罗马帝国相关的载入报错、首都未发现告警、缺科技的法律全部清零（v40）。

### 4. 其他子模组

- **国家命运深度整合**（3845632867）与**兼容桥**（3845632818）：随主模组同步，修复一处本地化键哈希冲突。
- **Glorp UI 1.4.9 凤凰适配增强**（3845632981）：快捷栏中文按钮加宽防截断，减少界面脚本报错。
- **地图美化 A/B/C**（3845632643 / 3845632683 / 3845632746）：同步版本号。

### 5. 实机验收（2026-11-26，EU5 1.4.9）

- 1444 拜占庭：开局只弹出 1444 年的路线抉择；AI 西渡航程 33 个月后于 1447 年在切萨皮克登陆，建立新国家。
- 1648 观察到 1655：清朝与日本的简介、清朝首都“北京”均正确，明清战争持续，大明退守广州。
- 1776、1821 载入正常；雄鹰陨落 476、632、768 载入正常，476 运行 16 个月。
- 书签界面 32 张新插图显示正常；凤凰指挥坞 5 个页签可用。

### 6. 已知问题

- 1648 开局载入时，游戏仍会清除约 400 条不合时代的政策（主要是民法与官房学政策）；1337 有少量国家的“大众教育”法律被清除。
- 启用“国家命运”时，奥地利在 1648、1821 开局几天后就改名“多瑙君主国”，1821 的统治者头衔显示“神圣罗马皇帝”。
- 部分草原部族在 1444、1776 的大厅简介仍是 1337 年的内容。
- 3 个价格修正没有图标。
- 1648 清朝统治者为多尔衮（史实应为顺治帝，多尔衮为摄政）。
- 第四罗马登陆后建立的国家宗教为天主教。
- 本轮没有实测：玩家亲自走完整条航程、新增局势面板与文化融合、法兰西与西班牙强权决议。

---

## 二、English Changelog

> **Status:** v40.0 release (EU5 1.4.9), covering everything from v31 to v40. The v40.0-rc1 candidate was tested in EU5 1.4.9 on 2026-11-26; the released files are byte-identical to the tested ones.
> **Saves:** v40.0 is **not** compatible with older saves. Please start a new game.
> **Fourth Rome:** now part of All-Eras Historical Bookmarks (3844848618). The old "1453 Fourth Rome" item (3845210560) is no longer updated; please unsubscribe and do not enable it with v40.0.

Made by: 寐夜空灵, miscos330

### 1. Main mod (3667460405)

- **Phoenix Command Dock:** a floating panel that overrides no vanilla interface, now with 5 tabs: imperial edicts, mass vassal directives, military-manual mobilisation and a new World Compass; 26 buttons with live status.
- **Byzantine core institutions:** new core institutions, 28 imperial Great Projects with their crises, theme escheatment and military manuals (v31, v36).
- **Six great powers:** Ottomans (Janissaries), Persia (Qizilbash and ghulams), Russia (Cossacks and the Zemsky Sobor) and India (mansabdars and universal harmony) evolve in three stages each; new France (Estates and absolutism) and Spain (Golden Age and Bourbon reforms) arcs; a 53-task British tree, the East India Company and Ming academies (v31, v39, v40).
- **Colonies:** 4 colonial autonomy and independence decisions with branching events; 30 dynamic colonial ensigns; no more doubled names such as "Viceroyalty of New Spain Viceroyalty" (v38, v39).
- **Peace and truces:** the Roman World arbitration resolution can only be proposed by the Roman leader and only covers the empire's subjects, so Byzantium is no longer forced into truces with a dozen neighbours; 26 redundant peace terms removed, two of which showed hostility as -4.00 (v38).
- **AI:** era-aware personalities and expansion goals. The Qing are no longer tagged "Eurasian Balancer" or sent along the Ming's Nanyang colonial route; vanilla "explore the African coast" no longer fires before 1415, in East or Inner Asia, or for landlocked states; the AI no longer keeps signing 5-year truces in peacetime (v40).
- **Storytelling:** 345 events rewritten with cooldowns against pop-up floods; 45 country descriptions that switch with era and culture, so 1648 Qing, Edo Japan and others no longer show their 1337 text (v38, v40).
- **Interface text:** all internal code names removed from player-visible text.

### 2. All-Eras Historical Bookmarks (3844848618)

- **Six eras:** 1204 / 1337 / 1444 / 1648 / 1776 / 1821, 32 theaters, 160 featured rulers.
- **1444.11.11, the day after Varna:** the fifteenth-century start moves from 1453 to 1444.11.11. John VIII of Byzantium chooses at once between holding Constantinople and sailing west to found a Fourth Rome (all of the former "1453 Fourth Rome" is included, with 5 3D wonders and its situations). An AI Byzantium advances the voyage every 6 months until landfall (v39, v40).
- **New 1821 era:** the Greek War of Independence and the Vienna system, a 30-state German Confederation, an Atlantic and Americas theater (v35–v39).
- **Bookmark art:** all 32 theater paintings redone to match their era and region (v39, v40).
- **Historical calibration:** adult historical rulers in every era, cross-continent tag fixes, 1648 colonial religions, 1821 state religions and capitals; the 1648 Ming–Qing war carries on as the Qing push south, the Qing capital shows as Beijing and Korea as Joseon (v37–v40).
- **Gameplay:** 10 era situations with their own panels, 17 era decisions (including cultural fusions), 24 world wonders, more than 1,400 adult historical characters (v39, v40).

### 3. The Fallen Eagle 361–768 (3845632550, standalone)

- 24 parchment theater maps and era banners, 39 featured flags redrawn (v37).
- 16 Late Antique and Roman provincial cultures; churches before the 1054 schism use period names, with Arianism and Hellenic paganism available; period-accurate names, titles and development (v38).
- 10 Late Antiquity situations, 16 decisions (6 cultural fusions), 18 wonders (v39, v40).
- Holy Roman Empire load errors, "capital not discovered" warnings and laws missing their technology all cleared (v40).

### 4. Other submods

- **National Destinies integration** (3845632867) and **compatibility bridge** (3845632818): updated with the main mod; one localisation key hash collision fixed.
- **Glorp UI 1.4.9 Phoenix edition** (3845632981): wider quick-bar buttons for Chinese labels, fewer interface script errors.
- **Map beautification A/B/C** (3845632643 / 3845632683 / 3845632746): version bump.

### 5. Live test (2026-11-26, EU5 1.4.9)

- 1444 Byzantium: only the 1444 path choice appears at the start; the AI voyage landed on the Chesapeake in 1447 after 33 months and founded the new realm.
- 1648 observed to 1655: Qing and Japanese descriptions and the Qing capital "Beijing" correct; the Ming–Qing war continues with the Ming falling back to Guangzhou.
- 1776 and 1821 load fine; The Fallen Eagle 476, 632 and 768 load fine, 476 run for 16 months.
- The 32 new bookmark paintings display correctly; all 5 Command Dock tabs work.

### 6. Known issues

- Loading 1648 still removes about 400 anachronistic policies (mostly civil law and cameralism); in 1337 a few countries lose a "mass education" law.
- With National Destinies, Austria renames itself "Danubian Monarchy" a few days into the 1648 and 1821 starts, and in 1821 its ruler is titled "Holy Roman Emperor".
- A few steppe hordes still show their 1337 lobby description in 1444 and 1776.
- 3 price modifiers have no icon.
- The 1648 Qing ruler is Dorgon (historically the Shunzhi Emperor, with Dorgon as regent).
- The realm founded after the Fourth Rome landfall is Catholic.
- Not tested this round: a player sailing the whole voyage by hand, the new situation panels and cultural fusions, the France and Spain decisions.

---

# 《凤凰计划（OEBYZ）》v30.2 更新日志（中英双语发布候选稿）

> **发布状态**：v30.2 正式版（EU5 1.4.9）。本版候选 v30.2-rc1 已于 2026-11-25 实机复测：1204/1337/1453/1648/1776、532/768 各开局均可进局并运行 1 年以上，无崩溃；上一轮反馈的 10 项问题实测已修复。
> **存档提示**：`v30.2` **不兼容旧版本存档**，请新开一局。

---

## 一、中文更新日志（GitHub Releases / Steam 创意工坊更新说明）

### 1. 旗舰新内容（v30.0–v30.2 全矩阵跃升）
- **五纪元全时代与 1204 第四次十字军（《全时代历史剧本拓展包》）**：
  - 正式扩展为 **`1204 / 1337 / 1453 / 1648 / 1776` 五大历史纪元**，配备 CK3 风格 5+1 地区战区选国界面与 **127 / 127 全员定制油画君主圆章**（含全新绘制的 `1204` 全 25 席油画肖像，彻底消除黑剪影占位）；
  - 新增 **157 位历史人物 3D 捏脸 DNA**（92 位 `1337–1776` + 65 位 `1204`，每角色完整 102 基因，服饰继续交由原版 `portrait_modifiers` 渲染）；
  - `1204` 开局拜占庭（`BYZ`）在大厅与开局动态显示为 **“尼西亚帝国”** 并加载 1204 专属史实背景文案（收复君堡后恢复拜占庭/罗马国号，零影响 `1337`/`1453` 原有文案）；补齐中世纪盛期时代、3 项思潮诞生修正、8 项 1204 静态修正及 11 项兵种史实描述。
- **古典晚期独立大修（《雄鹰陨落：361–768》）**：
  - 升级为 **6 纪元古典晚期独立大修**（`361 / 395 / 476 / 532 / 632 / 768`），全新重构 **6 纪元 CK3 图集书签界面**（顶栏 6 纪元完整显示不裁切、返回键无遮挡、532 展示 8 张旗舰油画、其余 5 纪元配 30 枚鎏金纹章圆章与独立开始按钮）；
  - 实装 4 个古典晚期时代（补齐 `age_format_*` 顶栏格式）、12 项古典晚期思潮与诞生修正、**176 位历史人物 3D DNA**（70 位 `532` + 106 位多纪元，每角色 102 基因）、28 枚 9 层 Mipmap DXT5 纹章贴图、6 座 3D 古典晚期奇观，并将 `532` 拜占庭显示名统一为 **“东罗马帝国”**。
- **3D 奇观、希腊动态地名、罗马大道与修道院（主模组 & 第四罗马）**：
  - 主模组新增 **3D 圣索菲亚大教堂**（`standard_building` 地图物件着色器，支持 `_mapobject` 与阴影四变体）与东罗马/瓦兰吉 **Skoutarion 鸢形盾**；
  - 新增 **19,539 条希腊语动态地名**、**155 段罗马帝国大道网络**、**12 座巴尔干历史修道院**与 **16 项安纳托利亚修道院兴复决议**；
  - 补全 **100% R29 原生 DDS 图标**，内置**凤凰历史百科**与**古典点唱机**；
  - 《1453 第四罗马》扩充至 **8 项帝国敕令与《帝国复兴》国际组织**，新增 **5 座 3D 极乐奇观**（圣母圣殿、大科通港、西方竞技场、新亚历山大图书馆、西方巨像）、极乐卫队 3D 兵模及新大陆希腊动态地名。
- **授权深度整合与视觉增强矩阵**：
  - **《国家命运（National Destinies）》授权深度整合包**：完整整合 `3668193813` 与中文汉化 `3744757513`（50,702 条中英双语 100% 对等），通过 `on_new_country_formed` 与年度对账钩子无缝同步凤凰 11 项旗舰建国链（另提供轻量《国家命运兼容桥》供直接订阅工坊原版使用）；
  - **《Glorp UI 1.4.9 凤凰适配增强》**：获 `3601047146` 授权深度适配，融合天朝秘书处宽幅决议标题并内置观察者模式季节控件保护（须排在播放集最底部）；
  - **《地图美化》三套风格预设（三选一）**：经典制图（Classic Atlas）、高对比政区（High-Contrast Political）、帝国羊皮纸（Imperial Parchment），均零着色器冲突并附带 2 个实时叠加地图模式。

### 2. v30.2-rc1 实机验收缺陷专项清零（对应 v30.1 全部 10 项反馈）
1. **顶栏时代格式键名清零**：补齐 `age_0_high_middle_ages` 与 4 个古典晚期时代（`age_la_1_twilight` / `2_migrations` / `3_renovatio` / `4_crescent`）的中英双语 `age_format_*` 词条，消除顶栏与 DHE 提示框键名裸露。
2. **303 位历史人物 DNA 报错清零**：为全时代（92 + 65 人）与雄鹰陨落（70 + 106 人）全部 333 位人物补齐 EU5 1.4.9 引擎必选的 5 项基础基因槽（`eyes` / `eyelashes` / `mouth_inside` / `beards` / `hair_styles` 中性默认值），彻底消除加载期 1,500+ 行缺基因报错，同时保持服饰零强行覆盖。
3. **雄鹰陨落 UI、纹章与 532 运行期噪声清零**：重做 6 纪元书签界面；将 28 枚 `oe_tfe_coa_*.dds` 迁移至原版正确路径 `main_menu/gfx/coat_of_arms/textured_emblems/` 并重导 9 层 Mipmap DXT5；补齐 12 项思潮诞生修正、全部 54 个事件 `outcome` 与东罗马国名；从根因清除 532 开局 19,251 行原版科技报错、2,295 行 `HRE doesn't exists` 报错与 91 行 `country_yearly.txt` 报错。
4. **1204 书签全面定稿**：补齐 `bookmark_1204_name` 中英标题；25/25 席全换定制油画肖像并重绘无剪影鎏金纹章兜底器；修正 1204 大厅尼西亚国名与开局背景文案穿帮。
5. **3D 圣索菲亚着色器修复**：由不支持地图物件批次的 `snap_to_terrain_alpha_to_coverage` 切换为原版 `standard_building`（完整具备 `_mapobject` 与 `Shadow_mapobject`），并完成第四罗马 5 座奇观与雄鹰陨落 6 座奇观的着色器静态核验。
6. **国家命运 `INJECT:form_effect` 失效修复**：清除深度整合包与兼容桥中的重复 `INJECT:form_effect` 死块，统一交由 `on_new_country_formed` + 年度对账执行；同步修复上游 `PLC_f` / `POL_f` 重复 `form_effect`。
7. **天朝秘书处“决议”标题截断与 GUI 布局修复**：移除主模组 `common.gui:586` 在布局容器子控件上的非法 `parentanchor = vcenter`，并在 Glorp UI `glorpUI_common.gui` 同步注入宽幅 `organization_resolutions_content` 覆盖块。
8. **Glorp UI 观察者模式季节刷屏清零**：为 `glorp.gui` 季节控件增加 `visible = "[GetPlayer.IsValid]"`，并将 4 条 `GLORP_UI_CURRENT_SEASON*` 词条改为延迟求值的 `SelectLocalization(GetPlayer.IsValid, ...)` 守卫。
9. **小项与本地化清债**：重命名 `oe_wp26_enc_532_gen_narses` 彻底消除 Murmur3 哈希碰撞；修复 1337 拜占庭军区开局事件计数为 0 的作用域偏差；微调 1337 大元中书省开局官僚维护与朝贡开销；修复 `lde_history_entries_replace_l_simp_chinese.yml` 中 `chaac_god` / `dzahui_god` 无效神祇引用（94 条报错清零）。
10. **防回归静态 CI 升级**：引擎静态规则库由 32 条扩展至 **36 条（72 项正反单测全绿）**，新增 `R33`（自定义时代 `age_format_*`）、`R34`（DNA 5 必选基因）、`R35`（`INJECT` 建国 `form_effect` 冲突）、`R36`（`map_objects` 着色器 `_mapobject` 校验）。

### 3. 已知事项与实机验证边界
- **书签预选国家说明**：EU5 1.4.9 原生书签按钮接口 `BookmarkView.SelectAndContinue` 仅负责选定开局年代进入大厅，不支持从书签界面直接锁定指定国家标签；进入大厅后请按推荐战区在地图上点选目标国家。
- **实机验证范围**：已实测五纪元与雄鹰陨落 532/768 开局、全栈（国家命运 + Glorp UI）与兼容桥、第四罗马启航至 1455 年；3D 圣索菲亚等 3D 模型、第四罗马登陆之后的内容、雄鹰陨落 361/395/476/632 开局尚未逐一目测。

---

## 二、English Changelog (GitHub Releases / Steam Workshop Change Notes)

### 1. Major Highlights (v30.0–v30.2 Full Matrix)
- **5-Era All-Eras Expansion & 1204 Fourth Crusade (`oebyz.phoenix.all_eras`)**:
  - Expanded to **5 historical bookmarks (`1204 / 1337 / 1453 / 1648 / 1776`)** with the CK3-style 5+1 regional theater selector and **127 / 127 bespoke oil monarch portraits** (including all 25/25 newly painted `1204` rulers — zero silhouettes anywhere).
  - Added **157 historical 3D character DNAs** (`92` for `1337–1776` + `65` for `1204`, complete 102-gene structure per character while leaving attire to vanilla `portrait_modifiers`).
  - `1204` `BYZ` dynamically displays as the **Empire of Nicaea** with authentic 1204 exile lore (reverting cleanly upon Constantinople's reconquest without affecting 1337/1453 BYZ); completed High Middle Ages formatting, 3 institution birth modifiers, 8 `1204` static modifiers, and historical EN/ZH descriptions for all 11 `age_0` unit advances.
- **The Fallen Eagle 361–768 AD Standalone Overhaul (`oebyz.phoenix.fallen_eagle`)**:
  - Expanded into a **6-Era Late Antiquity overhaul (`361 / 395 / 476 / 532 / 632 / 768`)** with a rebuilt **6-Era CK3 Atlas bookmark UI** (all 6 era tabs cleanly visible, unobstructed Back button, 8 flagship 532 oil portraits + 30 gilded heraldic medallions, explicit Start button).
  - Ships 4 Late Antiquity ages with `age_format_*` loc, 12 institutions & birth modifiers, **176 historical 3D DNAs** (102 genes/char), 28 mipmapped DXT5 heraldic COA emblems in vanilla's `main_menu/gfx/coat_of_arms/textured_emblems/`, 6 custom 3D monuments, and `Eastern Roman Empire` (`BYZ`) localization.
- **3D Landmarks, Greek Toponymy, Roman Roads & Monasteries (Main Mod & Fourth Rome)**:
  - Main Mod adds 3D **Hagia Sophia** (`standard_building` map-object shader), Byzantine/Varangian **Skoutarion** shield, **19,539 Greek dynamic place names**, **155 Roman imperial road segments**, **12 Balkan monasteries**, **16 Anatolian monastery restoration decisions**, 100% native R29 DDS icons, built-in **Historical Encyclopedia**, and **Classical Music Player**.
  - `1453 Fourth Rome` expands with **8 imperial edicts**, the *Restored Empire* IO, **5 custom 3D Elysian Great Wonders**, Elysian Guard 3D units, and Greek New World toponymy.
- **Authorized Expansion & Visual Matrix**:
  - **National Destinies Deep Integration** (permitted integration of `3668193813` + ZH `3744757513`, 50,702 EN/ZH keys synced with Phoenix formables via `on_new_country_formed` + yearly reconciliation; plus a lightweight **ND Compat Bridge** for standalone Workshop users).
  - **Glorp UI 1.4.9 Phoenix Overhaul** (permitted integration of `3601047146`, harmonized Celestial Secretariat resolutions & observer-safe season guard — always place last in playset).
  - **Map Beautification (3 Pick-One Presets)**: Classic Atlas, High-Contrast Political, and Imperial Parchment — zero-shader conflicts + 2 additive live map modes.

### 2. v30.2-rc1 Live-Test Fix Sweep (10/10 Issues Resolved Offline)
1. **Age Format Localization**: Added EN/ZH `age_format_*` keys for `age_0_high_middle_ages` and all 4 Late Antiquity ages (`age_la_1..4`), removing raw keys from the topbar and DHE tooltips.
2. **333 Historical 3D DNAs Completed**: Added all 5 EU5 1.4.9 mandatory neutral base genes (`eyes`, `eyelashes`, `mouth_inside`, `beards`, `hair_styles`) across All-Eras (`92 + 65`) and Fallen Eagle (`70 + 106`), eliminating 1,500+ startup gene errors while keeping zero wardrobe overrides.
3. **Fallen Eagle UI, COAs & 532 Runtime Hygiene**: Rebuilt 6-era bookmark UI; relocated & re-encoded 28 `oe_tfe_coa_*.dds` (9-mip DXT5); defined 12 missing institution birth modifiers, all 54 event outcomes, and Eastern Roman Empire display names; resolved root causes behind 19,251 advance errors, 2,295 `HRE doesn't exists` lines, and 91 `country_yearly.txt` errors.
4. **1204 Polish**: Added `bookmark_1204_name`, shipped all 25/25 oil portraits + upgraded heraldic fallback renderer, and fixed dynamic 1204 Nicaea name & non-anachronistic history text.
5. **3D Hagia Sophia Shader**: Switched to vanilla `standard_building` (full `_mapobject` & `Shadow_mapobject` support) and verified all Fourth Rome & Fallen Eagle monument shaders against vanilla `.shader` files.
6. **National Destinies `form_effect` Fixes**: Removed dead `INJECT:form_effect` blocks in favor of `on_new_country_formed` + yearly sync, and converted upstream `PLC_f`/`POL_f` to clean `REPLACE:` blocks.
7. **Celestial Secretariat Resolutions Header & Layout Fix**: Removed illegal `parentanchor = vcenter` at `common.gui:586` and synced the widened `organization_resolutions_content` blockoverride into Glorp UI's `glorpUI_common.gui`.
8. **Glorp UI Observer-Mode Season Guard**: Added `visible = "[GetPlayer.IsValid]"` in `glorp.gui` and lazy `SelectLocalization(GetPlayer.IsValid, ...)` guards on all 4 `GLORP_UI_CURRENT_SEASON*` keys.
9. **Minor & Loc Cleanups**: Renamed `oe_wp26_enc_532_gen_narses` (zero Murmur3 hash collisions across 353,620 keys); added country-scoped `oe_theme_setup_creatable_count` fixing the 1337 BYZ opening theme count mismatch; calibrated 1337 Great Yuan bureaucracy/tribute opening upkeep; replaced invalid `chaac_god`/`dzahui_god` references with `tlaloc_god` (94 errors eliminated).
10. **Expanded Static CI (36 Rules / 72 Unit Tests)**: Added preventive gates `R33` (`age_format_*`), `R34` (`persistent_dna` 5 mandatory genes), `R35` (no duplicate `INJECT:form_effect`), and `R36` (`map_objects` `_mapobject` shader verification).

### 3. Known Notes & Verification Scope
- **Bookmark Country Pre-Selection**: EU5 1.4.9's `BookmarkView.SelectAndContinue` selects the start date only and cannot pre-select an individual country tag before entering the lobby; choose your realm on the lobby map after loading the era.
- **Live verification**: all five eras plus Fallen Eagle 532/768 starts, the full stack (National Destinies + Glorp UI), the compat bridge and Fourth Rome up to 1455 were played in EU5 1.4.9 without crashes; 3D models, post-landing Fourth Rome content and the 361/395/476/632 starts were not individually inspected.

---

# 凤凰计划测试版 v25.0 更新日志

## v25.0《殖民 4.0 与全时代》（整合 v24.0 与 v25.0，2026-11-24）

- **起点：** v23.0（2026 年 11 月 24 日）。本版把“第四罗马 / 新极乐世界”从主模组拆出，单独做成新子模组；主模组只保留 1337 主线。
- **测试状态：** 2026-11-24 在 EU5 1.4.9 上实机测试 rc2→rc5，共 4 轮。rc5 测了三组：
  - **只开主模组：** 1337 匈牙利开局，观察到 1344 年；
  - **主模组 + 全时代子模组：** 1776 西班牙开局，观察到 1785 年；
  - **主模组 + 1453 第四罗马子模组：** 1453 拜占庭开局，观察到 1462 年。
  - 三组都没有崩溃。观察期间本模组运行期报错：1337 局 8 行（道路提示），1776 局和 1453 局各约 25–30 行，都来自同一处神罗决议提示。
  - 开局时有一批殖民内阁条件提示，三局各出现一次，玩家看不到。
  - 以下内容逐项实机核对过：殖民 4.0 决议中文标题、海外征服移交事件、殖民地统一命名、1453 开局两个抉择事件、清与吞武里国名，以及后世时代 1337 专属内容不再误触发。

### 主要内容

- **殖民系统 4.0（`oe_col4_`，零原版覆写）：**
  - **海外移交与整并：** 赢下海外战争后，若同大区已有殖民领，会弹出移交事件，可以把新占领土交给殖民领、只保留沿海要港，或全部留在本土直辖；另有《整合海外殖民飞地》决议。
  - **统一命名：** 14 个文明家族 × 134 个地区的美洲与大洋洲殖民地名。例如 1776 年测试中，丹麦的北美殖民领叫“文兰总督领”，葡萄牙的叫“巴西总督国”；也适用于海外新建的藩属。
  - **新内容：** 9 个新世界与大洋洲可成立国家、外围部落大瘟疫灾难与部族酋邦改革、征服者和平期转为殖民领、殖民总督文化路线。
  - **哥伦布大交换（宗教改革时代起）：** 两项决议，加上内阁行动《跨洋农作驯化局》，严格保护金银与香料产地。
- **1337 欧亚二梯队大国补全：** 为 18 组国家补上专属改革、特权、内阁行动、决议与错峰事件，全部只在 1337 开局生效：
  - 奥斯曼、法兰西、英格兰、卡斯蒂利亚/阿拉贡、葡萄牙、勃艮第、奥地利、波希米亚、波兰-立陶宛、莫斯科、瑞典、丹麦、匈牙利；
  - 威尼斯/热那亚、米兰/佛罗伦萨、马穆鲁克、后伊尔汗波斯诸国、德里、元明转换、日本。
  - 实机看过的只有卡斯蒂利亚和匈牙利的内阁行动与决议。
- **平衡与 AI：** 离线审计了全部自定义改革、法律、内阁行动与修正的叠加上限和代价，并补齐 AI 采用权重。条顿属国利沃尼亚开局忠诚度改为 60%；4 项通用危机内阁行动收紧了出现条件；首日决议和内阁列表减少无关条目。
- **全时代子模组（`OEBYZ-Phoenix-All-Eras`）：**
  - 1453、1648、1776 三套剧本的疆域、宗教、军队、战争和国号重做，含大清帝国、吞武里暹罗；
  - 后世开局修好了大批 1337 专属内容的报错，例如安德洛尼卡三世、1337 国际组织、科技模板；
  - 1453 开局不再弹出 1337 专属事件。
- **新子模组 · 1453 君士坦丁堡围城与第四罗马（`OEBYZ-Phoenix-1453-Fourth-Rome`）：**
  - 1453.4.6 剧本加完整的“第四奥德赛 / 新极乐世界”剧情、建筑、任务树与总督府；
  - 君士坦丁十一世开局可以选择死守城墙，或立即携圣物西渡建立第四罗马。
  - 主模组不再包含这部分内容，想玩第四罗马请订阅这个子模组。
- **描述扩展升级到 1.2.3：** 内置的 Descriptions Expanded 升级到 1.2.3（只有文字修正）。

### 子模组

- **全时代剧本合集**（`OEBYZ-Phoenix-All-Eras`，创意工坊 `3844848618`）：排在主模组之后加载。
- **1453 君士坦丁堡围城与第四罗马**（`OEBYZ-Phoenix-1453-Fourth-Rome`，创意工坊条目见主模组页面的链接）：排在主模组之后加载。

### 已知问题

- 本版不支持 v23.0 及更早版本的旧存档，请新开一局；只适配 EU5 `1.4.9`。
- 两个子模组都带有 1453 剧本，**同时启用的情况没有测试过，请二选一**。
- 已内置 Descriptions Expanded，无需另外订阅。如果同时启用 Descriptions for Every Tile 或 Every Historical Character，请把它们排在凤凰计划之上。
- 全时代书签页里，君主详情卡的“◀ 总览”按钮仍然点不动；点顶栏的时代页签可以回到总览。
- 1776 年测试中，AI 新建的美洲殖民领多数是“封臣”类型，而不是原版的“殖民领”类型；殖民 4.0 的移交和命名对两种都生效。
- 尚未逐项实测：18 组 1337 新内容中，除卡斯蒂利亚和匈牙利以外的各国；9 个可成立国家；大瘟疫灾难；第四罗马西渡之后的全部剧情；以及超过 10 年的长局。

---

## v23.0《十字与鹰旗》（整合 v22.0 与 v23.0，2026-11-24）

- **起点：** v21.0.1（2026 年 11 月 23 日）。对比 v21.0.1：事件 `3,559 → 3,661`（`+102`），决议 `404 → 458`（`+54`，全部严格归属原版 7 类），专属任务树 `55 → 64` 份（`+9` 树 / `+108` 项任务），原生 `.dds` 美术与图标 `1,406 → 1,418`（`+12` 幅 1080×440 专属油画），双语本地化各增 `+2,196` 条（增量 100% 对齐），新增 15 部法律、2 套文明议会、6 项内阁行动、6 支条顿跨时代兵种与 9 个零夺地建筑型附庸（专属附庸保护锁 `27 → 33` 类）；开局游戏规则 `18/18`、主线调度槽位 `98/98`、新增原版覆写 `0`、`CMDLOG=0` 不变。
- **测试状态：** 2026-11-23 至 24 日在 EU5 1.4.9 上实机测试 rc1→rc4（主模组与四合一子模组同时加载）：1337 开局 6 组新探针（P23–P28）全部读数 1111；干净观察者局 1337→1356 两轮（rc3、rc4）均无崩溃，本模组运行期报错为 0；12 张新油画逐张实机预览正常；条顿 5 大辖区与汉萨 4 商站在 1342 年前后均为忠诚附庸；1337 开局后世国家缺政体报错与飞地回退已清零。四合一书签页实机核对：4 个时代单击切换、20 张君主肖像、点击圆徽展开右侧详情卡、难度标与底栏扩展包图标条正常，界面布局报错为 0。

### 主要内容

- **v22.0 条顿骑士团重塑与黑十字×白十字双团路线（`oe_teu_` / `oe_thh_` / `oe_tom_` / `oe_kni_`）：** 重校 1337 条顿、利沃尼亚与医院骑士团开局疆域及 4 部骑士团专属法；新增 5 个神罗零夺地建筑型大辖区（波希米亚 `OTB1`、奥地利 `OTB2`、勃兰登堡 `OTB3`、梅尔根特海姆 `OTB4`、科隆 `OTB5`）、条顿总议会（Generalkapitel）、3 项内阁行动与 6 支时代 1–6 特色兵种；实装七阶东方大封邑（Ordensmark）与北方十字军原生局势界面 + 16 项条顿任务树；新增医院骑士团 12 项罗德岛—马耳他—耶路撒冷任务树及与条顿的《黑十字×白十字圣约》联动，配套 6 幅专属 1080×440 油画。
- **v23.0 教皇国《地上天国》与拉丁希腊帝国（`oe_pap_` / `oe_lat_`）：** 新增教皇国 16 项任务树、阿维尼翁返罗马、教皇特使团与《地上天国 / 圣彼得罗马帝国》双轨终局（含大公会议和解与东西教宗联动）；新增拉丁希腊七邦（亚该亚、雅典、纳克索斯、塞浦路斯、奇里乞亚等）重铸拉丁帝国与《分封协议（Partitio）》16 项任务树、加泰罗尼亚走廊与三方十字军剧情。
- **v23.0 意大利共和国《罗马共和国 S.P.Q.R.》与欧陆四星风味（`oe_spqr_` / `oe_hbg_`）：** 威尼斯、热那亚、比萨、佛罗伦萨可通过 16 项任务树、罗马元老院议会与行省总督（Proconsul）重光古典罗马共和国；新增吕贝克/汉萨 4 座零夺地海外商站（伦敦钢院 `OHK1`、布鲁日 `OHK2`、卑尔根 `OHK3`、诺夫哥罗德 `OHK4`，33 类专属附庸保护锁全覆盖）及勃艮第中法兰克、格拉纳达安达卢斯、黑海哥特—日耳曼四条 8 项任务树与 6 幅专属 1080×440 油画。
- **1337 飞地回归与历史清理：** 将 v15.0 费拉德尔菲亚（`OPH`）及 v17.5 地图整编永久合入 1337 生成管线与 G02 门禁，修复卡斯蒂利亚督军区 `spanish_language` 报错并清零全部跨时代休眠国报错。
- **新子模组 · 四合一全时代仿 CK3 剧本合集（`OEBYZ-Phoenix-All-Eras`）：** 单包整合 `1337`（零覆写原版）+ `1453` + `1648` + `1776` 四大纪元，取代此前的单年代 1453 / 1648 / 1776 剧本子模组与开局精选页 3.0；选时代界面重制为古羊皮纸历史版图（4 幅 `1920×1080` 地图 + 20 位手绘君主圆徽 + 彩色难度标），支持顶栏四世纪单击切换、点击圆徽或名单在右侧展开君主详情卡（肖像、政体/文化/宗教/难度与 20 篇双语传记），以及底部统一状态栏与原生扩展包图标条。

### 子模组

- **四合一全时代仿 CK3 剧本合集**（`OEBYZ-Phoenix-All-Eras`，创意工坊 `3844848618`，GitHub Release 附 ZIP）：排在主模组之后加载，勿与旧单年代 1453/1648/1776 剧本或开局精选页 3.0 同载。

### 已知问题

- 本版不支持 v21.0.1 及更早版本的旧存档，请新开一局；只适配 EU5 `1.4.9`。
- 四合一子模组 `OEBYZ-Phoenix-All-Eras` 已完整包含 1453 / 1648 / 1776 三个剧本，启用时请排在主模组之后，**切勿与旧版单年代 1453 / 1648 / 1776 剧本子模组或开局精选页 3.0 同时勾选**。
- 受 EU5 1.4.9 引擎限制，游戏规则、难度、铁人模式与成就开关在选完年代进入下一步选国大厅（Lobby）后设置，书签页底栏仅作只读提示；点击君主详情卡的「开始」将进入该时代选国大厅。
- 四合一书签页：国旗位目前全部显示为空框（含 1776 俄国），君主详情卡的「◀ 总览」按钮点击无效（切换年代即可回到总览）；不影响选年代与开局。
- 1453 / 1648 / 1776 开局日志里仍有一批原版科技文件的宗教比较提示（主模组 1337 专有的 18 个附加国家在后世时代缺宗教模板），不影响开局与游玩。
- 尚未逐项实测的：各新任务树中后期全部 108 项任务的逐一触发、教皇国/拉丁帝国/罗马共和国中后期全部事件分支，以及超过 1356 年的百年长局走势。

---

## v21.0.1 热更新（2026-11-23）

- **修复：** v21.0 正式版里，所有国家的决议面板都显示成空白条加提醒铃铛、看不到标题也点不了：v21.0 把全部决议改到了自定义分类，而原版决议界面只显示 7 个原版分类。v21.0.1 把 404 条决议全部归回原版 7 类（国家特色 / 扩张 / 政府 / 宗教 / 经济 / 其他 / 基建），保留的 6 个旧分类也改成原版排序号，以免引用它们的内容再出问题。实机核对过：拜占庭开局决议面板的标题、横幅和顶部 7 个分类标签都恢复正常，本模组运行期报错为 0。
- **新增：** 同时首次发布 **1453 / 1648 / 1776 三套独立剧本子模组**（都要排在主模组之后）：1453 君士坦丁堡前夜与文艺复兴（创意工坊 3844754950）、1648 威斯特伐利亚与明清鼎革（3844755248）、1776 启蒙时代与帝国黄昏（3844755348）。实机冷启动核对过：穆罕默德二世、路易十四、顺治帝、路易十六（法兰西王国、称国王）、叶卡捷琳娜二世、约瑟夫二世等君主名与序号正确，三套剧本的开局两选事件都能弹出，上一轮日志里的无政体空壳国家、超龄角色、旧君主任期、未来日期、摄政引用与编码问题均为 0。
- 三套剧本开局日志里仍有少量提示：约 8 条“随机生成君主”、3 条继承方式提示、3–5 条原版灾难引用早期角色，以及数百到数千条原版科技文件对引擎内置系统国（DUMMY/PIR/MER）的宗教比较提示；不影响开局与游玩。
- 1776 年俄罗斯的国旗看起来像英国米字旗，尚未核实原因。

## v21.0《帝国经纬·全量深化版》（2026-11-23）

- **起点：** v20.0（2026 年 11 月 23 日）。对比 v20.0：事件 `3,365 → 3,559`（`+194`），决议 `359 → 404`（`+45`），原生 `.dds` 美术与图标 `1,393 → 1,406`（`+13` 幅 1080×440 专属油画，另重绘 `44` 枚 512×512 成就双态图标），双语本地化各增 `+3,086` 条（中文 `55,024 → 58,110`，英文 `56,738 → 59,824`，增量 100% 对齐）；开局游戏规则 18 条、主线调度槽位 98/98 不变（所有 v21.0 周期逻辑均挂载于全局年度内核，零新增槽位）。
- **测试状态：** 2026-11-23 在 EU5 1.4.9 上分三轮实机测试（rc1→rc2→rc3）：1337 开局 13 组新探针（P10–P22）全部达到预期读数；观察者局 1337→1361（24 年，约 9 分钟）没有崩溃，本模组脚本运行期报错为 0（rc1 同一段约 17,000 行，来自法律 2.0）；金帐汗国 1337–1361 年拥有地块稳定在 409–414 块（rc1、rc2 都在 1343–1349 年崩到不足 100 块）。极乐洲新罗马（`ELR`）建国后，议会类型为“极乐新罗马元老院”，冷却结束后实际走通了“新君士坦丁堡 → 选择极乐议题 → 议会已召集”；投票结果没有等到。首轮查出的加载期与运行期问题（法律 `has_estate`、征讨败战回调、内阁行动语法与缺词条、总督区同色与人力效率等）已在 rc2/rc3 复测为 0。发版文件夹本身另做了加载检查：进主菜单，以拜占庭开局并推进数月，没有崩溃，本模组脚本运行期报错为 0。
- 没有逐项实测的：6 套新局势界面视觉、13 张新油画与 44 张重绘成就图逐张核对、极乐新罗马议会投票结果与 75 年三段经济曲线、察合台 14 对 3 东西分裂细节、41 条 T2/T3 任务树与 6 场中后期灾难的逐个触发，以及开局精选页 3.0 与 v21.0 同时使用。

### 主要内容

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

### 子模组

可选子模组（均需排在主模组 `OEBYZ-Phoenix-v21.0` 之后加载）：
- **开局精选页 3.0**（24 国双页画廊）：沿用 v20.0 版，创意工坊 `3844347953`；没有和 v21.0 一起重新实测。
- **1453 / 1648 / 1776 三套独立剧本**还在修，本版不发布：实测时 1648、1776 的多位君主序号显示错误（如路易十四显示为路易十一），修好并复测后再单独发布。
- 原声带子模组仍不发布（无编译音频库）。

### 已知问题

- 本版不支持 v20.0 及更早版本的旧存档，请新开一局；只适配 EU5 `1.4.9`。
- 1337–1361 的观察者局里，金帐汗国在 1357 年撤去护盾后到 1361 年仍未出现原版大混乱；更晚的走向没有测。
- 主模组仍保留少量历史遗留加载提示（43 个后期融合文化开局无人口、若干早期版本的旧改革/特权图标提示等），均不影响正常游玩。
- 极乐洲新罗马建国事件（`oe_ely.13`）若玩家一直不选且取消暂停，超时后会自动留在旧大陆残余国家；正常手动点击“率众西渡”即可无缝切换至 `ELR`。

---

# v20.0 及更早的更新日志（原文保留）

## v20.0（整合 v15.0 至 v20.0，2026-11-23）

- **起点：** v14.5（2026 年 11 月 23 日）。对比 v14.5：事件 `2,641 → 3,365`（`+724`），原生 `.dds` 美术与图标 `1,265 → 1,393`（`+128`），中英词条各 `46,623 → 56,797`（约 `+10,170`），开局游戏规则 18 条、主线调度槽位 98/98 不变。
- **测试状态：** 2026-11-23 用 v20.0 候选做了实机测试：加载检查（相对 v14.5 发版包逐条比对新增报错）、九组引擎探针一键跑通（P1–P9 读数全部为通过值），以及观察者长局 1337→1812（475 年，约 260 分钟）零崩溃、无卡死。首轮查出的 11 类问题（5 种新商品缺修正类型与 50 张修正图标、4 种不进人口需求、一份开局外交文件解析失败、两处高频运行期报错、4 个决议分类无效、12 个生产方式利润超出引擎区间、20 个消息类型和 66 条词条缺失等）已在 rc2 修掉并复测清零加载期与早期高频报错。发版文件夹本身另做了加载检查：进主菜单和开局画廊，以拜占庭开局后转观察者推进到 1340 年，没有崩溃，本模组脚本的运行期报错为 0，50 条修正缺图标提示已消失。rc3 修的那 5 类报错要 1362 年以后才会出现，修好后没有再跑长局复核。
- 没有逐项实测的：决议栏里每条决议的可见性（只有离线时代锁审计为 0 作证据）、各国专属任务树与 v15–v20 新增事件的逐个触发、以及 rc3 修正在 1362 年以后的长局表现。

### 主要内容

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

### 子模组

可选子模组：**开局精选页 3.0**（24 国，两页 3×4 画廊）在创意工坊条目 3844347953 更新，GitHub 附 ZIP；实机核对过两页 24 张卡片的国旗、悬停提示和翻页按钮，选卡后能以拜占庭开局。1453、1648、1776 三个剧本子模组还在制作，本版不发布。原声带子模组本版也不发布（没有编译好的音频库，游戏里放不出声）。

### 已知问题

- 观察者长局最远跑到 1812 年；更晚的内容（终局大战、1836 封卷等）没有在长局里出现过。
- 金帐汗国在观察者局里 1345 年前后先崩后复、1355 年后再崩（v14.5 的四局走势相同，原因未查明）。
- 雇佣兵在中亚、朝鲜等地刷“重步兵”时，加载日志有“找不到可用兵种”的引擎提示（未证实与本模组有关）。
- 发版包里有几十张 v14.5 留下的旧改革、特权图标，对应条目已经不存在，加载日志会提示“图标没有对应对象”，不影响游戏。
- 13 幅新事件插画暂时借用现有油画，之后补画。

---

# v14.5 及更早的更新日志（原文保留）

- **起点：** v11.8（2026 年 11 月 22 日）。
- **终点：** 2026 年 11 月 23 日。
- **游戏版本：** 欧陆风云 5，1.4.9。

## 写在前面

- 本次从 v11.8 到 **v14.5（整合 v11.8.2 / v12.0 / v12.2 / v13.0 / v13.5 / v13.6 / v13.8 / v14.0 / v14.5）**。对比 v11.8：事件 `2,377 → 2,641`（`+264`），原生 `.dds` 美术与图标 `1,106 → 1,265`（`+159`），开局游戏规则 `17 → 18` 条，主线调度槽位 `93 → 98`（已排满），中英词条各增约 3,600 条。
- **不支持旧存档：以前任何版本的存档都不能用于这一版，请新开一局。**
- **测试情况：**上一个候选包在 2026-11-22 至 23 日做过实机测试：一局 1337 拜占庭局和两局大元局，用控制台逐项跑了上一轮查出的问题和大元 3.0 的界面与事件；四局纯观察者 `1337→1380/1390`（合计约 190 年），零崩溃、无卡死。查出的问题（四局里大明都在 1364–1372 年间被大元整个吞并、可选子模组的标题显示成原始键等）随后做了修正，就是现在这一版。**这些修正没有再进游戏复测（修后未实机复测）**，只过了离线检查，发版包另做过一次加载检查（到主菜单并以拜占庭进局）。更早的 v14.0 候选跑过一局观察者 `1337→1463`。整体仍按“实验性测试版”发布。
- 没有逐项实测的内容和已知问题见仓库首页 README 的“已知问题”。下面“分版本明细”里写的是设计与实现内容，其中标注为修正的条目（尤其是 v14.5 的大元平衡与子模组修正）没有再进游戏复测。

## v14.5

### 主要内容

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

### 已知问题

- 旧存档不支持，请新开一局；只适配 EU5 `1.4.9`。
- **这一版的修正没有再进游戏复测（修后未实机复测）。** 其中最大的一项是大元与大明的平衡：上一个候选包的四局观察者里，大明都在 1364–1372 年间被大元整个吞并、大元一直存续；这一版为此改了红巾期间大元的征召与军费修正、给电脑控制的大元加了“朝纲尚振 / 派系崩解”分叉、加强了大明起事，改后的实际结局分布还没有看过。
- **观察者长局最远只到 1463 年**（v14.0 候选的一局）；v14.5 的四局只到 1380–1390 年。更晚才出现的内容——1500 年以后的各战区事件、近世疫病（1460 年起）、终局大战（1750 年起）、1836 年封卷——没有在长局里出现过。
- **只用控制台触发或抽看过、没有以玩家身份完整走过的内容：** 协调会 12 项决议逐项提案、天朝 2.0 事件、6 套 AI 性格；驿道署三种路由模式和地图上的实际铺路、殖民 3.0 事件；v13.0 的大部分事件；大师与名作、16 项和约条款、名城宪章、部队技能、摄政；天朝 3.0 的明、清两轨称号，四套新任务树；上都库里台、高邮罢相等大元事件的各个选项。
- 没有在不装官方拓展包的环境里测过（设计上不依赖拓展包；本机 5 个拓展包都装着）。
- 情境音乐：脚本已不再报错，但实际有没有切曲没有人验证过。
- 49 幅重绘插画是 AI 生成后人工筛选修整的。
- 打开帝国柱石面板、或切换到别的国家时，日志会一次多出几千条界面报错（旧问题，不影响使用）。大元开局第一个月会连弹三十多个“独占贸易权”首相报告（原版月结行为）。
- 年度观察者数据导出（规则 #16）默认关闭，需要的话在开局规则里打开。
- 印度教国家没有学派选择界面，两个新的印度教学派通过事件“斯里兰甘的大祭”采用；撒马尔罕星表学派可在事件“星表告成”里采用。
- 日志里仍有的提示：部分新外交交互没有消息类型（“Failed to find message type”）、部分价格没有修饰符类型，都不影响使用；原版自带的若干脚本报错不是本模组带来的。
- 军区（建筑型国家）不能自行招募正规军：这是原版引擎规则（与汉萨同盟相同）。

### 分版本明细


#### 1. `v11.8.2` — 极乐洲新罗马（`ELR`）彻底脱壳抹视野
- **全新独立标签与完整脱壳**：第四奥德赛西渡北美后不再借壳旧 `BYZ`，而是依托美东无旧大陆视野原主完成原子脱壳，成立独立帝国标签 **`ELR`（极乐洲新罗马帝国）**；旧大陆 `BYZ` 战争、附庸、军队与领土干净交割退场，绝不泄漏旧大陆视野。
- **旧大陆 100% 漆黑 + 美东 15 大区全亮**：实测登陆后欧洲 `0 / 5,838`、亚洲 `0 / 9,473`、非洲 `0 / 3,019` 全黑迷雾，美东沿海 15 大区与百慕大完整点亮，还原纯粹的新大陆拓荒沉浸感。
- **科技清单传承与思潮免接纳费**：通过脚本清单（`oe_ely_advance_copy.txt`，共 1,059 条逐项检测条目）自动复制旧主体在全 6 时代已研究的对应科技，并向已接纳思潮同步注满 `100%` 进度（月结自动生效，另赠 6 个月 `-100%` 思潮接纳费便于即刻手动接纳）。
- **皇室搬家、开国舰队与切萨皮克粮仓修复**：干净迁移君主、继承人与最多 6 名朝臣；修复切萨皮克开局粮食赤字（月粮产转正盈余、首都注粮 `+500`、鱼 RGO 上限 `+2`）；彻底锁死旧拜占庭灾难（`oe_fate_of_the_phoenix` / `oe_byzantine_intrigue`）与旧大陆事件，避免在北美弹出旧世界干扰。

#### 2. `v12.0`（Wave 7 · 主线槽位 `94–96` · 规则封顶 `#18`）— 万国协调会、天朝 2.0、史诗 AI 与情境原声
- **欧亚世界协调会与 12 项原生 IO 投票决议（Slot `94` `oe_con_`）**：
  - 创立 1648+ 近代多边组织 **`欧亚世界协调会`（`oe_io_eurasian_concert`）** 与条约中立缓冲法域；
  - 新增 **12 项原生国际组织投票决议**（三大组织各 4 项）：
    - *罗马世界（4 项）*：《罗马和平停战仲裁》《帝国联合禁运》《普世护教联军动员》《边疆行省纳入罗马外延法域》；
    - *中华天朝（增量挂接原版 `middle_kingdom`，0 覆写，4 项）*：《勘合朝贡重估》《东亚开海/禁海诏令》《天朝靖边讨伐令》《四海大都护府敕建令》；
    - *欧亚世界协调会（4 项）*：《维也纳/君堡万国和会》《反霸权均势围堵公约》《全球海峡航行公约（海洋自由 vs 海洋封闭）》《国际海港检疫卫生协定（直连 `v11.0` 近世疫病！）》。
- **天朝 2.0 深化（0 槽位）**：开放 8 项天朝外交交互的受保护 AI 逻辑（内置中原防边界碎裂锁与区域白名单，AI 绝不乱拆腹地）；新增第 9 项投下改行省交互与「**召藩入宿卫**」人物交互；新增 `oe_cel.25`–`.30` 6 幕东南亚/丝路/海疆羁縻事件。
- **全球史诗 AI 性格与外交编排（Slot `95` `oe_aip_`）**：新增 **6 套动态历史 AI 战略性格**（严格让位于财政紧缩守卫 `oe_ai2_fiscal_austerity`，防 AI 破产），新增 10 项外交目标、10 项扩张目标、8 项扩张权重、4 项参战规则与 16 项全球宿敌标准（引导葡萄牙夺霍尔木兹/果阿/马六甲、防欧洲荒诞介入日本内战与天朝跨洲乱入欧洲战争）。
- **Wwise Tier-1 原版无 DLC 情境音乐导演（Slot `96` `oe_aud_`）**：严格基于 **81 首原版验证安全曲目**（`0` DLC 依赖、`0 MB` 音频膨胀），为 14 幕史诗节点精准切曲，并附带 6 主题点播台 `oe_aud.90`。
- **开局规则 `#18` 永久封顶**：新增 `#18 欧亚万国协调会、史诗战略性格与情境原声`（标准全开 / 仅协调会、决议与原声以兼容第三方 AI 模组 / 关闭）。
- **清零 `v11.8` 4 处历史微瑕 + 47 张 BGRA DDS**：修正东亚终局战区锚点（秋田 `toshima` → 江户 `toshima_kanto`）、重新接入 2 条孤立事件（`oe_rel2.10`/`.13`）、消除测试键哈希碰撞 `3709841899`、补齐 23 枚历史缺失修正图标。

#### 3. `v12.2`（Wave 7.5 · 0 槽位）— 帝国驿道署与殖民 3.0 全面进化
- **原创《帝国驿道署》（`oe_road_`）**：
  - 人类玩家独享的 **O(N) 有向生成树自动修路引擎**，严格走真实金币扣款与真实修路工期（`construct_road`，绝不作弊秒铺），配备**双层国库红线保护**，且只读自动避让外部修路模组；
  - 支持 **3 套智能路由模式**：① 邻近度主干网、② 市场港口与工场商路网、③ 文化同化 2.0 冲刺网；
  - 内置文明道路确定性择优阶梯（优先铺设罗马大道 / 西伯利亚驿道 / 站赤驿道，并于 `v13.0` 升级为 **8 级阶梯**接入印加皇家驿道！）。
- **《殖民 3.0》（`oe_col3_`）**：
  - 新增 2 座海外核心建筑：**官办拓殖募民局** 与 **海外总督行署**（`local_proximity_source = 35`，让海外据点自身成为邻近度与铺路枢纽！）；
  - 无内阁三联方案彻底根治海外新市场 `+0 待定` 移民停摆痛点；
  - 新增《特许商社法》（3 项政策）、2 项殖民内阁行动、3 项决议、12 篇大航海与殖民地博弈事件（商社分红、银船、卡塔兹、私掠、倾茶、**《帝国联邦宪章》**等）与 7 条历史 AI 殖民走廊（含天朝防乱涂非洲守卫）；新增 16 张 BGRA DDS（含 6 幅 Tier-S 油画）。

#### 4. `v13.0`（Wave 8 · 主线槽位 `97–98` → `98 / 98` 圆满封顶！）— 启蒙科学、非洲三轴与美洲本土活史诗
- **启蒙科学革命（`oe_sci_` · 0 槽位）**：新增 3 类科学大师、3 类科学名作、4 套印刷工场生产方式与 4 座启蒙地标建筑（奥斯曼 **穆特费里卡印书局**、**伦敦皇家学会**、清代 **《四库全书》与钦天监**、**《百科全书》编纂馆**），配套 3 项内阁、5 项科技、1 律 3 策与 13 篇事件，打通「识字率 → 传世著作 → 思潮催化 → Age 5–6 科研跃迁」非战高光流派。
- **非洲三轴文明史诗（`oe_afr_` · Slot `97`）**：完整打造 **所罗门埃塞俄比亚（`ETH`）**（扎拉·雅各布宗教改革 + 祭司王约翰跨红海联纵）、**马里 / 桑海（`MAL`/`SON`）**（廷巴克图桑科雷大学 + 迎战 1591 摩洛哥火绳枪远征）、**斯瓦希里基尔瓦（`ZAN`）与大津巴布韦（`ZMW`）**（印度洋季风黄金贸易网与反制葡属封锁）三大轴线，含 2 学派、3 地标、6 科技、19 篇事件。
- **美洲本土三帝国 + 极乐洲深度双向联动（`oe_amr_` · Slot `98`）**：
  - **阿兹特克（`TNC`）**：三城同盟、奇南帕浮田农艺综合体、激活原生纳瓦特尔 **4 项宗教焦点**，零 DLC 软联动特奥蒂瓦坎太阳金字塔与乔卢拉圣城；
  - **印加（`CSU`）**：四万公里 **印加皇家驿道（*Qhapaq Ñan*）** 自动接入《帝国驿道署》8 级阶梯，配结绳户籍与抗疫韧性；
  - **易洛魁联盟**：若极乐洲新罗马存在，双向触发《切萨皮克罗马盟邦公约（*Foederati*）》引入马匹火器，或组建泛北美长屋反罗马联盟（无极乐洲时自然回退欧洲殖民接触线）。
- **跨文明合奏（`oe_syn_` · 0 槽位）**：新增 8 幕跨大洲联动大事件（含红海祭司王、纸页子午线、基多赤道测绘、跨洋本草与**《98/98 万邦启明合奏》**终章）与 28 张 BGRA DDS（含 16 幅 Tier-S 油画）。

#### 5. `v13.5`（Wave 9 · 0 槽位）— 传世大师名作、16 项历史和约、制度精雕与 12 国开局精选
- **传世大师、12 件史诗名作与 16 处零 DLC 奇观圣地联动**：新增 8 类大师职业、8 大类可掠夺/归还艺术品与 30 篇事件（涵盖《六书》、塞奥法内斯变容圣像、贝赫扎德《布斯坦》、唐英《陶冶图说》、徐光启《农政全书》、雪舟山水长卷、狩野永德《唐狮子图》、圣马可天文钟、布劳大地图集等 12 件巅峰名作）；对 `D015` 8 座古代奇观与 `D017` 8 处世界圣地做纯地点零 DLC 软联动加成！
- **16 项历史外交和约条款库（`oe_pt_*`）**：涵盖《威斯特伐利亚主权与“教随国定”》《尼布楚划界与边市协定》《库楚克-凯纳吉海峡自由通航》《〈海洋自由论〉强制开海》《废除卡塔兹海洋垄断》《强制归还掠夺传世名作》（物理回迁原产地名作！）、《天朝册封与奉表朝贡》《拆解列强霸权宣称》《海外特许商馆》《永久和平》《强制宗教宽容》《边疆非军事化》《丝路商队豁免》《白银岁币赔款》《典籍抄本引渡》《吊销私掠特许状》。
- **军事技能、名城宪章、特色摄政与日本四大神道教派**：
  - **8 项陆海部队战术技能**：希腊火虹吸突袭、战车大营宿营、龟船铁甲破阵、八旗铁骑突贯、铁炮三段击齐射、骑士道长矛操演、坑道工兵爆破围城、巨型桨帆侧舷齐射；
  - **16 项欧亚非美名城宪章**（丝路驿市、江南丝织市镇、浮梁御窑、市舶司番坊、堺港会合众、威尼斯德意志商馆、汉萨自由港、马六甲万国船长、卡利卡特季风港、奇南帕浮田等）；
  - **8 套特色摄政体制**（含抢占原版选举机制的威尼斯十人委员会紧急摄政、波兰首席大主教、幕府大老、阿塔贝格、牧首与元老监国等）；
  - **4 派日本神道教派**：`INJECT:shinto` 零覆写接入**吉田、度会、垂加、两部**四大神道教派 + 10 项原生宗教派系动作。
- **12 国开局精选双层剧本（`oe_scenarios.txt`）**：在开局精选页与游戏内同步呈现欧亚非美 **12 大旗舰主角**，配 Day-1 开幕导览卡与随时可翻阅的 4 页交互典籍《十二主角典藏名录》；新增 48 张 BGRA DDS。

#### 6. `v13.6`（Wave 9.5 · 0 槽位）— 柱石 UI 大瘦身、极乐洲 2.0、天朝 3.0 与 46 项新任务
- **帝国柱石 4 栏清爽 UI & 两部新编年史**：拜占庭帝国柱石主标签由 **9 栏瘦身为 4 栏**（`概览 | 行政令 | 军区 | 熵增`），概览页顶部置入紫金编年史大按钮与 `改革 / 财政 / 琼筵序次` 3 子入口，军区补员定额优雅折叠进军区面板，删除冗余盾牌与成员卡；新增**《天朝四海编年史（只读）》**（14 节点）与**《极乐洲新罗马编年史（只读）》**（16 节点）。
- **极乐洲新罗马 2.0（`oe_el2_`）**：新增专属附庸 `极乐洲总督区`（`oe_ely_exarchate`）与 **10 大上下文智能一键总督区**（美洲 6 督 + 故土 4 督）；新增 1490–1560《跨洋大重逢》（6 轨检测君堡实控者）、《赫斯珀里得斯东征前进基地》、《真·双头大帝跨洋分封大诏》；新增严格门控可选风味国**文兰（Vinland）**与**斯巴达尼亚（Spartania）**（非极乐洲局 0 触发、永不抢人类地）；新增**极乐丝绸御坊**与**新君堡希腊火船坞** 2 座御用工场并接入驿道署商路网。
- **天朝日不落 3.0（`oe_cel3_`）**：新增 **10 大跨洲一键敕设大都护府**（覆盖西域至美洲，全图 28,574 地零区重叠、永不割天子首都）、**40 条四朝自适应动态国名规则**（元 / 明 / 清 / 汉字圈与客帝自动换称）、**「万国来朝」5 年周期经济回流**（4 类稀缺市场需求 + 贡市商力 + 天命 + 阶梯贡银）与太平洋/印度洋/协调会双日外交事件链。
- **任务 × 局势正交精修 + 4 套新任务树（共 +46 项任务）**：拜占庭主线 `oe_msn_01_byz` Branch B（任务 `05–08`）全面兼容军区附庸与内政财政达标路径，不再与局势抢地；新增 **`ELR` 极乐新罗马（16 项）**、**`ETH` 埃塞俄比亚（10 项）**、**`TNC` 特诺奇蒂特兰（10 项）**、**`CSU` 印加（10 项）**四大专属任务树，全模组累计达 **29 国 346 项专属任务**！

#### 7. `v13.8`（Wave 10 · 0 槽位）— 49 幅博物馆级 Tier-S 历史油画重绘大工程
- 将 `v11.0`（11 幅）、`v11.2`（6 幅）、`v11.8`（8 幅）、`v11.5`（16 幅）全部 **`41 / 41` 幅**程序占位插画（40 幅事件油画 + 1 幅欧亚终局大战局势图），连同 `v13.6` 的 **`8 / 8` 幅**专属大图（5 幅极乐洲 2.0 + 3 幅天朝 3.0 正式油画），**100% 替换为 `1080×440` 32-bit 无压缩 BGRA 博物馆级历史油画**。
- 全部 49 幅成图均经反向解码接触表与局部四角目检，彻底清除假文字、假签名、切头切桅与红蓝反色，实现全包 **`0` 程序占位画**。

#### 8. `v14.0`（Wave 11 · 0 槽位）— 全线终局精修、22 里程碑冠冕与可选书签子模组
- **全仓标度根治**：修复全模组历史遗留的 14 处小数 `subject_loyalty` 标度问题（统一归整为 EU5 原生 `0–100` 整数制），同步修补 `oe_col3` 免费建造理由与 `oe_flv_insults` 同名标签陷阱。
- **1836 典藏《帝国年代纪》封卷升级**：里程碑扩充至 **22 项**（新增双头大帝总督府、八方大都护、九十八槽万邦大共和国、帝国驿道与传世名作典藏 4 项压轴成就），新增 5 级巅峰徽印与**《一八三六全线终极冠冕大典》**（三大终极冠冕荣誉与永久加成）；`ELR` 自动归入罗马《帝国年代纪》史官体例。
- **O(1) 跨波次遥测 2.0（`oe_bal2_`）与 14 项全量 CI 硬门禁**：建立覆盖主线槽位、覆写白名单、双语本地化、编码规范、利润率、28,574 地表引用、静态修正、孤立事件与 DDS 哈希的 14 项自动化总审门禁。
- **独立可选伴生子模组 `OEBYZ-Phoenix-Bookmarks`**：以零侵入架构把 3×4 十二主角典藏画廊与原版欧洲地图切换按钮独立封装为可选子模组，保持主模组 0 字节 GUI 污染。

#### 9. `v14.5`（Wave 12 · 0 槽位）— 大元帝国 3.0 全面重做 + 上两轮实机验收查出问题的修正

##### 9.1 大元帝国 3.0 全面重做详情
- **受管红巾军局势三补丁（受管覆写白名单 `66 → 69`）**：
  - **顶栏「至正平乱枢机仪」**：在原版红巾军局势面板顶部原生嵌入四维仪表盘——`平乱之势（0–100）`三刻度拔河条（`30` 颓势 / `50` 相持 / `70` 中兴）+ `朝议清浊`、`钞法与国库`、`京仓漕粮`三联 KPI 状态卡；
  - **9 项原生态局势动作**（零覆写挂接红巾局势）：
    - *大元 6 项*：`起复/委任平乱大帅`、`发行至正新钞/整顿盐课`、`海运征粮/疏浚会通河`、`敕调投下宗王勤王`（消耗忠顺宗王真实人力而非凭空刷兵）、`行省便宜行事（行枢密分院）`、`调停元廷将帅内讧`（1360+ 专属救命键）；
    - *义军 3 项*：`弥勒降世·广纳流民`、`高筑墙广积粮·军屯实边`、`檄文北伐·驱逐胡虏`。
  - **彻底根除火星兵与不合理机制杀（含 `rc2` 平衡校准）**：
    - 人类大元总征召惩罚经精确对冲维持在约 `-23%`（`oe_y7_rtr_yuan_crisis` `-35%` + `oe_y7_strife_levy_floor` `+12%`，绝不再跌到 `-95%~-100%` 零征召，也不会出现 `rc1` 意外叠加成正加成的现象）；
    - 为 **AI 大元**独立引入 `45%` 朝纲尚振 vs `55%` 派系崩解的开局分叉，并在 AI 高邮罢相（`oe_y7.12 a`）时移除征召托底并施加 AI 专属崩盘修正（人类大元零惩罚）；
    - `oe_y7` 凭空免费兵团削减约 **65%**（最多 `67 → 23` 支历史近卫），大明起事免费正规团设为 **4 支**（原版 8 支的一半、删除第 2 次火星瞬刷），修复兜底君主漏存作用域导致 `.36` 失火的问题，义军民心加成精确封顶 `1.25×`（`+25%` 士气 / `+5%` 纪律 / `+35%` 征召战力），起义初控改用 `local_control` 条件收敛至合理 **约 `55%`**；
    - 软化「沙河夜惊」与「高邮罢脱脱」自残剧情杀（移除全军 `-30%` 兵力蒸发与白送敌方 `+20` 战分），修复 `oe_y7_court_command` 反协同 BUG 与 `1368.1.1` 硬悬崖，消除 `oe_pmng`/`oe_sit_yuan_restoration`/`oe_sit2`/`oe_yr2` 四处跨模块碰撞；
    - 修复郭子兴早死导致大明整局卡死的原版缺陷，加入朱氏汉人宗室护栏彻底根除 **1451 孛儿只斤明王 BUG**；删除辽阳/吐蕃事件中的 `abandon_location`，**杜绝东北/吐蕃随机弃地变白地**；修复红巾局势提示 `owner ?= c:CHI`、原版 `casus_belli` 与 `bayad_dynasty` 报错，并接入大明灭亡诊断日志以便实机核验。
- **大元宗王体系 2.0（`oe_yw`）**：
  - 10 位实土投下宗王全面实权化：忠诚 `≥70` 每王反哺大元 `+1.5%` 骑兵战力与 `+2%` 人力上限（满 10 叠 `+15%` 骑战 / `+20%` 人力），低忠则触发离贰索赐危机；
  - **中原八城「五户丝」动态财税抵扣**：实盘对接淄川、历城、益都、恩州、阳翟、福安、钜野/任城、高唐 8 处食邑，每守 1 城直接抵扣 `5%` 年度岁赐，8 城全保**直省 40% 中央岁赐现金**；
  - 诸王面板每行新增 **3 项实体按钮**（`赐金印` / `虎符勤王` / `折钞改土`）；修复投下改普通附庸（`oe_cel.25 b`）后继续白吃岁赐的变量泄漏；
  - 升级扬州镇南王、武昌威顺王、庐州宣让王**三大出镇亲王行府**（配面板三联状态卡与三路抉择），统一十年**上都库里台盛会**（`oe_yw.20`）。
- **大元十一行省 2.0（`oe_yp`）**：
  - **外交容量吸血直降 85%**：6 内地建筑行省外交容量占用由 `0.25 → 0.00`，3 边疆行省由 `0.50 → 0.15`，总占用由 **`3.00 → 0.45`**；云南（`LNG`）与征东（`KOR`）并入行省总表，配顶部腹里中书省卡，完整呈现**「腹里中书省 + 十大行中书省」十一行省帝国总账**；
  - **5 大地域治理画像 + 独立藩镇权重（`0–100`）**：财赋漕运省（江浙/江西）、中原兵冲省（河南江北/湖广）、关蜀天府省（陕西/四川）、三边铁骑省（岭北/辽阳/甘肃，联动驿道署优先铺站赤！）、藩领特省（云南/征东），彻底告别 Tier 2 空壳与千省一面；
  - 行省表每行新增 **4 项实体按钮**（`行枢密` / `御史台` / `括漕盐` / `改三司`）及 **12 篇高光行省互动事件（`oe_yp.30`–`.41`）**，收尾直通「行省改三司 vs 铁骑大行省」御前大辩论！

##### 9.2 `v14.0-rc1` & `v14.5-rc1` 实机验收点名问题修复清单
- **可选子模组 `OEBYZ-Phoenix-Bookmarks` 大厅画廊完整修复（P1-1 / rc2 P1-2）**：左键「开始新游戏」直进 3×4 十二主角画廊，右键或点击下方独立按钮「自由选国大厅（全图模式）」直进全图选国；`rc2` 同步补齐 `BYZ`/`VEN`/`JAP` 三面原版旗帜（`BYZ_eagle_imperial_crown`/`VEN_peace`/`JAP_monarchy`）与 11 国 `<TAG>_LONG` 中英标题，12 国卡片标题与旗帜完整呈现。
- **开幕导览卡开局必弹（P1-2）**：`oe_v135_pulse.txt` 改挂原生大厅后钩子 `on_game_started_after_lobby` 并加幂等月脉冲兜底，选 12 主角进局 2 天内必弹本国导览卡 `oe_scn.1`–`.12`。
- **音乐导演脚本报错清零（P1-3）**：移除 `post_audio_event` 不被解析器接受的 `player = root` 键名并改由 `is_human = yes` 前置守卫，彻底消除 14 条音乐脚本加载解析报错（注：音频实际发声待玩家有声环境复核）。
- **`has_law` 裸键纠偏（P1-4）**：修复殖民 3.0 与科学革命 4 处 `has_law = law:*` 前缀错误。
- **文兰 & 斯巴达尼亚零报错真建国（P1-5）**：在无主纽芬兰调用 `create_country_from_location` 前执行原子预归属与清核收尾，解决文兰建国失败报错。
- **日本神道四大派系自动入会与图标补全（P1-6）**：为任意神道国家增加自动加入 `international_organization:shinto` 兜底机制，补齐 4 枚神道派系专属图标（零粉框），进入神道 IO「派系」页签即可完整运筹四大派系。
- **上一版实机点名加载报错全部清零（P1-7 ~ P1-10 + rc2 P2-1/2）**：补齐 59 条缺失中英词条、30 条 `main_menu/gui/messagetypes/` 消息类型及全部 30 项 `_MAP` 中英词条、10 项神道 AI 动作清单、13 项 `modifier_type_definitions` 与 15 枚修正图标、4 条 `@trigger_no!` 前缀；将 4 套启蒙印刷工场 PM 利润精确校准至 `25.00%`；修正 5 项名城宪章重色与 `oe_el2_greek_fire_arsenal` 人力/水手效率合规值；91 个历史无 BOM `.txt` 统一归整为 UTF-8 BOM + LF；`rc2` 移除孤儿事件 `oe_yr2.9` 与未用修正 `oe_y7_relief`，并清理 `#18` 非法格式标签。
- **全线运行期体验精修（含 `rc2` 补充）**：
  1. `oe_ely.13` 脱壳逻辑迁入隐藏事件 `oe_ely.130`，弹出瞬间 332 条干跑提示报错清零；`rc2` 将旧壳切共和与皇室迁移移至 `change_player` 之后的 `oe_ely_dissolve_old_host`，彻底消除「共主邦联」与「政府重塑/看守政府」冗余弹窗；
  2. `ELR` 新罗马换装帝紫红底金色皇冠双头鹰专属国旗，开国舰队调整为 Age 1 合法 5 艘（3 运输 + 2 德罗蒙桨帆），赠 6 个月 `-100%` 思潮接纳费修正；易洛魁「北疆烽烟」与「和平使者」单次触发；
  3. 双头大帝选项一迁都君士坦丁堡时永久保留切萨皮克核心三地直辖，极乐工场文案动态读取实际首都名；
  4. 恢复帝国柱石「琼筵序次」子视图顶部主插图；修复 `oe_byz_dynastic_honors.txt:16` 进局空国家作用域报错；
  5. 欧亚协调会 `ordered_great_power` 补加 `check_range_bounds = no` 零越界；
  6. 观察者遥测台 `oe_bal.90`/`oe_bal2.90` 增加 `is_ai = no` 护栏（注：规则 16 年度遥测默认关闭，观察者局需手动开启）；
  7. 帝国驿道署新增 O(1) 轻量年度 AI 修路脉冲；大元宗王开局大厅后立即注册（首日即显 10 位藩王），三大行府按钮补齐指挥官空判与面板三卡即时刷新；
  8. 修复 `oe_ymar.3`、`oe_mo.4` 与 `oe_y7_m` 未初始化等多处观察者残留运行错。

---

## v11.8

### 一、《第四奥德赛 · 极乐洲新罗马》（v10.5，可选，开局规则 #13）

- 君士坦丁堡陷落后（也可设为 1337 年提前启航，或整个关闭）率众西渡，在大洋彼岸登陆立国。四幕：圣火西渡与登陆、立国与元老院及极乐希腊文化、三教抉择（联动罗马多神教，新增 2 尊西海神祇与 10 项神谕）与新军团战舰、大西洋争霸与重返故土。57 个事件、10 项决议。

### 二、全欧亚六条主角线与 25 国任务（v10.0）

- 金帐与帖木儿、马穆鲁克、波兰—立陶宛、威尼斯与热那亚、大明双轨、女真与满洲六条 500 年主角线；欧亚经济 2.0 与教务 2.0；25 个国家各一套任务包，共 300 项任务，不覆写原版任务。134 个事件。

### 三、暗影、海洋、佣兵与历史大危机（原定 v12.5，提前并入；开局规则 #14）

- 谍报、宫廷密谋与王朝外交（5 项国家交互、3 项人物交互、6 项内阁行动）；私掠特许、海峡通行税等 3 种宣战理由与 5 次历史远航；雇佣兵契约与自由军团哗变灾难；小冰期与十六世纪白银价格革命两场灾难、12 项议会诉求和按史实写的叛军纲领。55 个事件。

### 四、近世疫病、后期霸权、终局大战与编年史（v11.0，开局规则 #15、#16）

- 1460–1750 年的两种近世疫病（黎凡特复发鼠疫、军营热）与双岛检疫港、陆疆封锁站；不覆写原版霸权的后期四维霸权与反霸张力；1750–1836 欧亚终局大战局势（四种结局）；典藏编年史与 1836 年评级；默认关闭的观察者年度数据导出。58 个事件、13 项决议。

### 五、天朝四海：分封、羁縻与都护（v11.2）

- 执掌天命的国家可以册封宗藩、设羁縻宣慰司与四海大都护府三类附属；4 部天朝法律、8 项外交交互、3 种宣战理由、按轨道变化的国名与官称，削藩与改土归流。24 个事件。

### 六、御用工场、区域产业、特色征召与军阵（v11.8）

- 6 座御用工场与 14 档可切换配方、6 项市场需求；6 个区域产业与 4 套用工制度；8 条序列 42 档特色征召兵（军区屯田兵、怯薛、射击军、哥萨克、西帕希、红头军、贵族总动员、曼萨布达尔）；4 陆 2 海共 6 种军阵与 4 套练兵法。

### 七、四大新战区（v11.5，开局规则 #17）

- 波斯与中亚、印度洋与次大陆、日本与朝鲜、西欧各有一座地标建筑、新法律、政府改革、阶层特权、4 项科技、4–5 项决议和 14 个事件，波斯与印度另有 5 个新宗教学派；通行证制度、抗通行证海盟、东行使团、渡海大战四件大事把四个战区连在一起。西欧这一线不需要任何扩展包。

### 八、实机测试后的修正（2026-11-22）

- 谍报外交与后期霸权两个模块共 8 项外交交互的“电脑前置条件”写法有误：观察者长局里每分钟刷约 8,600 条脚本报错。已改成原版的写法，复测为 0。
- 终局大战、极乐洲、两帝之争三个读数事件把数值显示成了错误文本，已修正。
- 14 个御用工场配方的利润（42%–167%）超出游戏自检范围（30%±1%），产出已按 30% 重新标定；工场建筑自带的产出加成不变。
- 雇佣兵欠饷风险的两个判断在灾难界面里会读到未设置的变量，已加保护。
- 私掠特许给受害国的“清剿海盗”宣战理由，对方没有港口或海军时会立即失效，现在只给能持有它的国家。
- 一个修正名与原版词条哈希相同（会互相覆盖），已改名。
- 印度教国家没有学派选择界面，两个新印度教学派改为在事件里采用；撒马尔罕星表学派同理。
- 八旗演武场与御窑两座建筑落成时会改一个还没初始化的变量，已加初始化。
- 教务 2.0 的 3 项决议用了不存在的决议分类名，已改成原版的“宗教”分类。
- 3 座建筑（极乐洲的两座、金帐的铸炮坊）的人力 / 水手产出超过引擎允许的上限，已调到上限。

## 已知问题

- 旧存档不支持，请新开一局；只适配 EU5 `1.4.9`。
- **观察者长局只跑到 1410 年。** 更晚才出现的内容——四大新战区 1500 年以后的事件、通行证制度 / 海盟 / 东行使团 / 渡海大战按年份自动出现、近世疫病（1460 年起）、终局大战（1750 年起）——没有在长局里出现过。
- **只经过加载和观察者长局、没有以玩家身份逐项走过的内容：** v10.0 的六条主角线与 25 国任务、v10.5 极乐洲四幕、谍报 / 海权 / 佣兵 / 小冰期与白银革命、终局大战和编年史的实际流程、天朝四海的分封与削藩。
- **四大新战区、工场、征召、军阵里没实地看过的：** 新政府改革要到对应时代才出现；四座地标建筑没有实地建造过；特色征召没有实际征召出来看兵种；军阵与练兵法没在军队界面里选用过；区域产业与用工制度没在界面里选用过。
- v11.0 以后新增的 120 张贴图（事件图与图标）是程序画的占位图，不是正式美术。
- 印度教国家没有学派选择界面，两个新的印度教学派通过事件“斯里兰甘的大祭”采用；撒马尔罕星表学派可在事件“星表告成”里采用。
- v9.9 遗留问题的复看结果：新决议的标题与说明已正常显示；军区开局选项 A 会建两个军区；进局时游戏的报错计数约 4,200 条（rc1 约 4.8 万行）。罗马多神教神殿面板“只显示 6 尊活跃神”这一项这次没有复看。
- 日志里仍有的提示：新外交交互没有消息类型（“Failed to find message type”）、天朝附属的纳贡价格没有修饰符类型，都不影响使用；原版自带的若干脚本报错（割让人口的和约、若干风味事件、圣战相关的内置钩子等）不是本模组带来的。
- 大元中兴局势节奏可能偏慢（v9.9-rc1 实机里 6 年进度 29/100），这一版没有调整。
- 军区（建筑型国家）不能自行招募正规军：这是原版引擎规则（与汉萨同盟相同）。
- 1337 开局头 20 天东正教农民减少约 6.1 万、大元建筑式行省偶尔加入原版独立运动，属于原版底层结算机制，仍在跟踪。

## 兼容性

- 只适配欧陆风云 5 `1.4.9`；不支持旧存档。
- v9.6 以来（含本版全部新内容）新增文件均为零新增原版覆写、零新增 GUI 覆写；与本机 28 个常见创意工坊模组的文件路径 0 新增碰撞。
- 西欧新战区不引用任何扩展包专属内容，与《Across the Pillars》同路径、同名文件均为 0；装不装该扩展包都能运行（两种配置下的冷启动没有分别实测）。

## v9.9

### 一、拜占庭《罗马多神教（Religio Romana）》深度重制与六柱万神殿（v9.8）

- **安全无损更名与原版错字修补：** 保留内部 ID `hellenism_religion` 以兼容原版 D008 与重建罗马，通过最高优先级本地化替换将全局宗教名与百科简介升级为 **「罗马多神教 / *Religio Romana*」**（支持 `.latin_language` 罗马/希腊双轨神名与免费典仪风格切换决议），并顺手修复 EU5 `1.4.9` 原版 4 处多神教词条死链与错字；无条件解锁神谕开关，不强锁 D008。
- **卡皮托利乌姆六柱万神殿（16 神池 / 10 新神 / 50 新神谕 / 103 枚专用图标）：** 在原版 6 尊神祇之外新增 **10 尊**罗马帝国与「罗马诠释（*Interpretatio Romana*）」跨欧亚合祀神祇——**无敌太阳、天后朱诺、圣火维斯塔、医神阿斯克勒庇俄斯、双面门神雅努斯、光明之神阿波罗、伊西斯—塞拉皮斯、复仇战神·奎里努斯、无敌密特拉、大母神库柏勒**（每神配 5 项动态缩放神谕，共 **50 项新神谕**）。转教后通过动态入祀轮换保持宗教面板 6 尊活跃神（`2 ADM + 2 DIP + 2 MIL`）；10 尊新神立像（`88×180` 暗/亮态）基于原版大理石雕像重绘合成，并配齐全部 103 枚专用 `.dds` 图标。
- **完整宗教制度与五百年四幕史诗（1337–1836）：** 新增 **8 个罗马宗教面向**（西比尔神谕书、维斯塔圣火团、世纪大典、大祭司长统领制、米斯特拉斯学园、众神和平宽容敕令、玛尔斯凯旋誓愿、帝国秘仪结社）、**2 套国家宗教律法**（8 项政策）、零界面覆写 **「罗马大祭司团（*Collegium Pontificum*）」国际组织**（含《罗马圣历协定》IO 律法）、**6 项古典祭仪行动**、**2 座拜占庭核心圣地**（君堡斑岩太阳神柱、米斯特拉斯圣院，不卡死原版转教条件）、**9 座可重修古典大神殿**与三阶「众神和平」自动修正、**4 项时代 5–6 科技**，以及 **35 个四幕史诗与祭仪事件**。所有转教入口严格限定仅人类玩家可控，AI 拜占庭不会自发改信多神教。

### 二、军区 2.0 重构与核心文明经典系统深修（v9.7）

- **军区 2.0 重构（回应玩家实玩反馈）：** 重调 6 类军区附庸参数（显著降低外交容量占用与相对宗主军力厌恶）；新增纯 C++ 自动修正将 MOD 军区忠诚档（0–3）直接同步至原版附庸忠诚度；1337 开局 `oe_theme_setup.1` 升级为**三选一**（默认推荐选项 A：仅立 2 个核心大军区——色雷斯—马其顿 + 塞萨洛尼基共管塞雷斯走廊，首日外交容量占用大幅下降，并支持后续随时拆分/整并）；新增 4 项「驭将之术」附庸交互与三阶段低忠危机（「先谈判、后平叛」）。
- **拜占庭支柱、豪族、内战与双轨罗马化 2.0：** 新增 26 幕事件与 5 项决议，细化四大豪族诉求与联姻、寒门拔擢制、1341/1352 内战筹码、塞萨洛尼基狂热派三结局及双轨罗马化与东西教会合一 2.0。
- **大元与可玩罗斯核心线 2.0：** 新增 27 幕事件、9 项决议与 2 项投下交互——大元银钞信用账本、江南海运漕粮护航（抗倭寇/风暴）、梁王/扩廓帖木儿/辽阳藩王交互；罗斯诺夫哥罗德市民大会商业共和深化、6 支哥萨克军团互动与特辖军三档节流。
- **五大枢纽市场需求桥接与 1.4.9 体验精修：** 君堡/威尼斯/热那亚/泉州（晋江）/亚历山大 5 大商贸枢纽接入原生 `add_temporary_demand`；新增 8 项中后期三文明内阁行动、6 项时代 3–5 阶层特权和平近代化转型，以及 3 项战时宗主战略指令与单体附庸战时角色委派。

### 三、欧亚 AI 2.0、殖民边疆 2.0、四速有机同化与全球宗教拓展（v9.9）

- **欧亚 AI 逻辑 2.0（`oe_ai2_`）：** 新增 15 条战略扩张走廊、12 条反边界癌与跨海止损评分规则、12 条分阶段历史目标、4 种欧亚史诗 AI 性格、8 项防死锁外交目标、2 条参战护栏、13 国合理宿敌范围、2 项非作弊财政紧缩护栏（无白送金币，以威望/扩张收缩换取利息与通胀稳态），以及 O(1) 年度 AI 宏观总管，赋能 6 大欧亚核心 AI 使用既有 MOD 改革/宫廷/钞粮/律法机制。
- **殖民与边疆拓垦 2.0（`oe_col2_`）：** 零覆写原版 3 个殖民宪章文件，独立新增 **4 个原创欧亚殖民宪章目标**（帝国远洋商馆与海外执政区、草原与西伯利亚哥萨克木堡、帝国边疆军屯、普世和平传教共处宪章）、5 类生态/补给限速（可通过港口/基建/内阁克服，不硬锁沙盒）、3 项边疆内阁行动、2 座边疆建筑与 4 选一原住民外交事件链。
- **文化四速有机同化与七大文化首都争霸（`oe_cul2_`）：** 用纯 C++ 地块自动修正实现**城市文教都会（+25%～+40%）/ 海港商贸枢纽（+15%）/ 低控无路偏远山区阻力（-35%～-50%）/ 边疆定居牵引（+20%）**四速有机同化；新增宫廷/礼拜/市场三语协同与 4 项语言资助行动、4 项独立少数族群自治特权、5 大欧亚文化融合弧，以及君堡/罗马/巴黎/大都/开罗/撒马尔罕/莫斯科 **O(7) 七大文化首都争霸**。
- **全球宗教原生引擎深化与 24 座新圣地（`oe_grel_`）：** 零覆写宗教本体，补强 **景教（东方教会与大元崇福司）**、**东方正统教（亚美尼亚/科普特/埃塞俄比亚）**、**伊斯兰瓦克夫多学者宫廷与哈里发法统**、**天主教东方政策与新教改革 8 面向**、**草原腾格里 4 神**、**印度教 6 化身**、**神道/上座部佛教**，共新增 **24 座全核验圣地**及 11 幕跨教派事件（含对罗马多神教复兴的只读跨教反应）。

### 四、政务减负、奇观修会、原生引擎金矿与 3D 兵模（v9.0 / v9.5 / v9.6）

- **品质收债与可视化仪表盘（v9.0）：** 清理全仓旧脚本静态债务与无主地块访问隐患；新增**开局规则 #11（同盟到期降级为保障独立开关）**；左下角快捷栏扩至 **8 钮**（新增「熵增」与「政务托管」），帝国柱石新增**熵增可视化总览页签**与 5 项顶栏精简提醒；上线远洋海外总督区 Plan A；补齐 23/23 跨时代兵种卡面、20/20 科技图标、34 幕事件油画与 8 套经典局势横幅（+83 `.dds`）。
- **政务自动化、议会、附庸、奇观与文化融合（v9.5）：** 零界面覆写可选**政务自动化总控台**（默认关闭，含续约与年度账单）；新增 **28 项欧亚议会议题**、**4 类新附庸与 24 项外交交互**、**12 座欧亚奇观 + 圣地 + 骑士团与东正教修会**（+45 `.dds`）、**18 项文化融合科技**与**开局规则 #12（动态思潮起源与欧亚催化）**。
- **原生 1.4.9 机制挖掘、3D 兵模与 LDE 批五（v9.6）：** 106 项决议全面重排至原版 **7 色分类栏**；新增 12 项顶部引导提示、5 套原生宗教律法（18 政策）与 10 项宗教面向、5 文明特色摄政与 5 项皇室教育圆章、3 条帝国大道五件套（帝国御道/蒙古驿道/西伯利亚大驿道）、3 项附庸军事姿态、30 条外交侮辱与 12 项死因；新增覆盖俄罗斯/大明/草原 18 国的零覆写 **3D 兵模体系**（复用原版已核验模型，修正大明时代 5–6 无辫子穿帮）及 **160 座欧亚非名城 LDE 批五百科**。

### 五、工坊文件碰撞审计与实机测试后的热修

- **28 个本地热门工坊模组碰撞审计：** 自 `v9.6` 起至 `v9.9` 新增文件坚持零新增原版覆写、零新增 GUI 覆写，对本地 28 个已测模组（含 `Refined Colonization`、`More Restricted Colonization`、`Construction Manager`、`OGAS Optimized`、`Standard of Living`、`Economic Overhaul`、`Accepted Culture Advances`、`Community Mod Framework`、`Bamboo King CFP`、`凯撒汉化` 等）保持 **0 新增文件碰撞**。
- **针对首轮实机测试（`v9.9-rc1`）的热修（只过了离线检查，修后未实机复测）：**
  - 修正军区 2.0 开局预览作用域报错与 1337 预置塞萨洛尼基军区（`BYT01`）未初始化/漏并塞雷斯问题；
  - 为全部 29 个新决议补齐 `.title`/`.desc` 双语词条，并在静态检查工具中永久加入 `DEC-LOC` 门禁（140/140 决议全覆盖）；
  - 为罗马多神教加入转教即执行 `remove_god` 清理未入祀新神的机制（目标是只留 6 尊活跃神、未入祀的神不再给加成），并将 10 尊新神立像升级为原版大理石基底合成质感，替换 3 幕基督教堂插画、统一罗马/希腊神名、补齐 `god_emperors` 页签词条与 `io_opinion_oe_romp_pontificate`；
  - 修正 50 年长局刷出 38.3 MB 报错的 `oe_cul2_owns_any_cultural_capital`（`owner = root → prev`）、`oe_ren_neo_leading` 未判空、`OeSit2YrFaction` 观察者作用域、`oe_obs_logger` 王朝判空、`oe_romp_on_action:64`、`oe_flv_imperial_roads`、`oe_wnd_order_callings`、`oe_sub_effects`、`oe_grel_triggers`、`has_policy` 多余前缀、12 个 `oe_ai2` 文件 UTF-8 BOM、3 座国内奇观改用 `local_merchant_capacity`、17 项行动补入 AI 列表及 `@trigger_no!` 图标前缀；清除政务自动化面板中的开发用语，并为 `is_ai = no` 决议条件包裹可读提示文本。

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

## 兼容性

- 只适配游戏版本 1.4.9。
- 不支持旧存档：以前任何版本的存档都不能用于这一版，请新开一局。
- MOD 改写了 1337 年开局的部分原版文件（国家、建筑、外交、国际组织、地区偏好）和几份原版事件文件（拜占庭、保加利亚、热那亚、塞尔维亚、奥斯曼的崛起等）。改同一批原版文件的模组大多不兼容，不建议同时启用。

## 借鉴与致谢

- **按许可集成：**国家、文化、王朝等的历史介绍文字来自“描述扩展：国家、文化、王朝及更多”（Descriptions Expanded，[创意工坊 3838927963](https://steamcommunity.com/sharedfiles/filedetails/?id=3838927963)），© Descriptions Expanded contributors，按 CC BY-SA 4.0 使用。凤凰计划在其基础上为自有的国家和家族补写了条目，并让两处文本与本 MOD 的原文合并；这些增补同样按 CC BY-SA 4.0 提供。详见包内 `third_party/descriptions_expanded/`。原许可、署名、来源清单和改动说明都在这个文件夹里。
- **军区辖区数据：**来自“拜占庭重置:涅槃”（Byzantium Overhaul: Nirvana，创意工坊 3602306286），经授权使用。
- **致谢：**感谢以下创意工坊模组。竹子大王的社区DLC（创意工坊 3763953914）：大元官服肖像（四档圆领袍、蒙古交领衣、蒙古帽、展脚幞头、垂翅幞头）与元廷六位人物（欧阳玄、许有壬、苏天爵、揭傒斯、泰不华、余阙）的能力估值，东罗马军队的单位模型（罗马盔、具装覆面盔、札甲、斯帕塔剑、鸢盾与扇形盾、拉布兰旗），大元军队的单位模型（护脸盔、札甲、范阳笠、绑腿、直刀与雁翎刀、虎头盾、半具装马铠）。模型与贴图照原样借用并改名，定义与挑选规则是我们自己写的，经竹子大王本人同意使用；文件清单见包内 `third_party/bamboo_king/`。下列模组给了我们结构或写法上的借鉴，脚本和文字都是我们自己写的：《The Reich / 帝国》（3823496063）——边疆定居的登记与核实、出资人的回报与赎回、战后分封（经营边区、战后安排），换地前按名单快照、只转仍归原主之地的写法与把原版立陶宛皈依包成可调用效果的写法（拉丁世界五期），“关键一块先到手、其余才做”的步骤顺序（塞尔维亚二、三期）；《Rise of the British Empire》（3621489583）——特许公司的分步解锁、两级买地、具名租让与“收归国有 / 退出”两种结局（罗马商社）；“拜占庭重置:涅槃”（3602306286）——按类别、只记不动钱的月账（军区账本）；《Basileia Romaion: 1337》（3618199037）——把地交给已定义而不在场的国家来让它复国（黑羊、白羊、伊梅列季、突厥诸侯）；《Refined Colonization》（3816832717）——商站的准入名单（招民垦荒）；满洲-清朝风味扩展（3714561641）——藩王附属类型的结构（投下宗王），朝贡觐见“按请求裁决、按对方收入计价”的事件结构与附属出兵的意愿（高丽），军粮储备的省份修正与省份粮食的读法（海运），通胀档位的写法与每月通胀的量级（钞法）；National Destinies（国家天命，3668193813）——“先选路线、再分三阶、每阶一张条件清单”的结构（大元中兴）；Praecepta Militaria - Propyrglon tou Dunabeos（3820674880）——“保护而非附庸”的单向关系的建立与撤销（塞尔维亚二、三期）；Flavorium Universalis - Rhomania（3791634667）——“丝路重开”修正的键组合与量级（中兴与霸业第三批）；MEIOU and Taxes（3735059838）——把通胀按小数读取的写法（钞法）。天朝拓展（Celestial Empire Expansion，3810799047）、Praecepta Militaria 系列、The Persianate World 和 Rhomania - a Journey To The West 的脚本注释里记下的引擎行为，帮我们查出并避开了几处问题。

制作：寐夜空灵、miscos330

---

# 凤凰计划测试版 v8.5 更新日志

- **起点：** v6.8（2026 年 11 月 21 日）。
- **终点：** 2026 年 11 月 21 日。
- **游戏版本：** 欧陆风云 5，1.4.9。

## 写在前面

- 本次是从 v6.8 跨越至 **v8.5（整合原计划 v7.0 / v7.2 / v7.3 / v8.0 / v8.5 全部内容）** 的年度旗舰大版本，游戏内容完整延伸至 **1337–1836 全五百年**：事件从 **1372 个增加到 1747 个（+375）**，中文词条（不含描述扩展词库）从约 **18300 条增加到约 23800 条（+5500）**，新增 **28 张原创高精度原生 `.dds` 美术资产**（5 套旗舰局势横幅 + 5 枚局势徽章 + 14 幅文明事件油画 + 4 张全欧亚主题载入界面，发布包因此增加约 59 MB）。
- **不支持旧存档：以前任何版本的存档都不能用于这一版，请新开一局。**
- **测试情况：**本版已对 v8.5 候选进行过 3 次完整冷启动、178 年纯观察者长局实机验证（1337→1515，零崩溃、无卡死），并在游戏里看过左下角的快捷导航栏、5 张局势横幅和一部分新事件图（4 张载入图没有刷到）、编年史 2.0（74 条线路），跑过海外总督区探针；随后针对实机暴露的 5 套局势节流、决议语法、13 张事件插画、1337 艾登自动保独、原版界面 8 条简中报错等全部问题完成了热修并全项通过 23/23 离线门禁。因热修批与 1560–1836 后期线路未再跑第二轮实机长局，整体仍按“实验性测试版”发布，欢迎在 Issues 或评论区附截图与 error.log 反馈。

制作：寐夜空灵、miscos330

---

## v8.5

### 一、三大核心文明 500 年全时代演进（1337–1836）

- **东罗马 / 罗马帝国近代线（1560–1836，v8.0）：**新增 33 幕跨时代主线（火药军改、希腊文艺复兴与启蒙辩论、地中海金融与工业近代化、宪政帝制与立宪危机、终局大决断），与原有 1337–1560 复兴线、凤凰灾难拆分及疆域三圈无缝衔接。
- **大元近代线（1450–1750，v8.0）：**大元守江山/中兴之后的近代化演进（神机营与新式火器、钞法与海运制度定型、两宫与诸王近代转型、南洋与西域经略），大元败亡时安全收束并兼容北元/明清格局。
- **俄罗斯玩家可玩全线（1337–1836，v7.0 + v8.0）：**全面升级莫斯科 / 罗斯可玩主线——莫斯科崛起与第三罗马宣称、伊凡雷帝与特辖制、动乱时代、哥萨克拓荒与西伯利亚东进，直到彼得大帝改革与近代帝国演进。
- **三国跨时代军事与兵种演进（v8.5）：**新增 **23 支跨时代特色兵种**（覆盖东罗马、大元、俄罗斯及六支边疆哥萨克军团，横跨 Age 1–6）与 **20 项专属军事科技**、8 幕军事演进事件及三大文明常规演训决议。

### 二、五大旗舰“局势”与全球多战区拓展

- **五大旗舰局势（全配原生 1080×440 横幅与 128×128 徽章）：**
  1. **大元中兴**（含全多国行动 1 年全局节流，防止 60+ 附庸短期刷满）；
  2. **金帐分裂与草原大乱**（金帐汗国细化为白帐、克里米亚、喀山、阿斯特拉罕、诺盖、西伯利亚等诸汗国分崩机制）；
  3. **拜占庭文艺复兴**；
  4. **东方十字路口**（中东、波斯与高加索霸权博弈）；
  5. **两帝之争**（东罗马 vs 神圣罗马帝国 / 奥地利 / 俄罗斯 / 教廷，含安全解散神罗结局）。
- **全球四大拓展战区（v8.5）与远洋线（v7.3）：**
  - **西欧与反罗马同盟：**法、英、西、奥及海上强权在东罗马重返意大利与西地中海后的动态外交结盟与宗教危机；
  - **南亚与东南亚海上丝路：**从红海、印度洋到马六甲的商站争夺、季风贸易与香料海权事件链；
  - **马格里布、巴巴里海盗与非洲总督区：**北非海盗袭扰、直布罗陀海峡封锁、跨撒哈拉黄金潮与复设非洲总督区；
  - **北欧、多瑙河与东亚边缘精炼包：**卡尔马联盟、厄勒海峡关税、波罗的海汉萨与东亚沿海边角史实事件补全；
  - **远洋殖民与海外总督区（v7.3）：**东罗马复兴后的远洋探索、殖民总督区与特许经营决议。

### 三、大帝国治理、反滚雪球与动态强权 AI

- **帝国熵增引擎（v8.5，游戏规则 #9 可自由开关/调档）：**解决中后期“一家独大后无事可做”的通病——随领土体量与时代推移衡量行政过载，与原有“罗马之重负”无缝合并（绝不双重扣减），提供改革减熵、地方分权与和平黄金时代等多条出路。
- **12 强动态反霸权 AI（v8.5，游戏规则 #10 可自由开关/调档）：**在 O(1) 极低开销下驱动欧亚 12 大主要强权（法、英、卡斯蒂利亚/西、奥、奥斯曼、马穆鲁克、波立、莫斯科/俄、帖木儿/波斯、德里/印度、大元/明、威尼斯）动态结盟抗衡过速膨胀的霸主。
- **10 项完整自定义开局游戏规则：**支持开局自由切换大元/罗斯历史走向、反滚雪球强度、帝国熵增引擎、12 强反霸权 AI 等全部开关。

### 四、UI 2.0、编年史 2.0、LDE 批四与原生美术升级

- **快捷导航栏与 UI 2.0：**主界面左下角新增可折叠的快捷栏，一键打开帝国柱石、罗马世界（大元是天朝中书）以及决议、政体、外交、动荡；实机看过，不遮挡地图模式栏。
- **凤凰编年史 2.0：**从 48 条扩展至 **74 条全文明线路**，拆分为 6 个 O(1) 零卡顿分页（5 大时代分栏），一目了然查看全图剧情进度。
- **历史介绍词库（LDE 批四）：**新增 9 支哥萨克文化、金帐五翼、3 大王朝、5 支宗教与学派历史介绍，并修净英文词条中文残留。
- **28 张原生高精度 `.dds` 美术资产：**5 张局势横幅 + 5 枚局势徽章 + 14 张文明与熵增事件油画 + 4 张全欧亚载入画面（已批量升级全模组 227+ 幕核心事件配图）。

### 五、实机排雷与原版 1.4.9 缺陷修复

- **实机暴露问题的热修（修后未实机复测）：**针对首轮实机与 v8.5 观察者长局里记到的问题做了修正——包括 5 套多国局势 3 个月刷满节流、远洋与演训决议语法重写、13 张错配/无背景事件插画目视替换、`oe_l7.txt:187` 亡国后的 443 次报错、`oe_ent.7` 1338 年穿帮早弹门控、补齐 32 条修正图标、以及 178 年长局里另外几处运行时报错。
- **1337 拜占庭—艾登自动降级保独的修正（不改原版文件，修后未实机复测）：**判断原因是 1337 开局同盟在正教/逊尼负好感下触发原版降级保独机制，现加了开局史实盟约好感加成 `oe_s37_umur_pact`（+60）来避免。
- **原版 EU5 1.4.9 缺陷修复（零 `.gui` 覆写）：**补齐 28 条原版缺失简中本地化键，并以零界面覆写补齐 8 条原版 `gui.log` 简中失效键；建立 85 份原版重叠文件 SHA-256 锁定基线，方便后续版本升级秒速排障。

---

## 已知问题

- 本版整体按“实验性测试版”发布：1337–1515 已跑过 178 年实机长局；v8.5-rc2 热修与 1560–1836 近代后期线路已通过全部离线门禁，尚未做第二轮实机复测。
- 旧存档不支持，请新开一局。
- 1337 开局头 20 天东正教农民减少约 6.1 万、以及大元建筑式行省偶尔加入原版独立运动，属于原版底层人口/外交结算机制，仍在持续跟踪。
- 军区（建筑型国家）不能自行招募正规军：这是原版引擎规则（与汉萨同盟相同）。
- 拜占庭部队模型在日志里有两类无害贴图/挂点提示（头盔多余 UV 通道、重步兵盾牌缺默认项），不影响游戏内显示。
- “两帝之争”局势中，6 项公开行动按拜占庭、神圣罗马帝国、奥地利、俄罗斯、教廷五方阵营分属显示，拜占庭视角看到 2 项属正常设计。
- 1430 年代奥斯曼处于苏丹国阶位时出现叠字国名，为 EU5 1.4.9 原版突厥王朝后缀规则，不影响游玩。

## 兼容性

- 只适配游戏版本 1.4.9。
- 不支持旧存档：以前任何版本的存档都不能用于这一版，请新开一局。
- MOD 改写了 1337 年开局的部分原版文件（国家、建筑、外交、国际组织、地区偏好）和几份原版事件文件（拜占庭、保加利亚、热那亚、塞尔维亚、奥斯曼的崛起等）。改同一批原版文件的模组大多不兼容，不建议同时启用。

## 借鉴与致谢

- **按许可集成：**国家、文化、王朝等的历史介绍文字来自“描述扩展：国家、文化、王朝及更多”（Descriptions Expanded，[创意工坊 3838927963](https://steamcommunity.com/sharedfiles/filedetails/?id=3838927963)），© Descriptions Expanded contributors，按 CC BY-SA 4.0 使用。凤凰计划在其基础上为自有的国家和家族补写了条目，并让两处文本与本 MOD 的原文合并；这些增补同样按 CC BY-SA 4.0 提供。详见包内 `third_party/descriptions_expanded/`。原许可、署名、来源清单和改动说明都在这个文件夹里。
- **军区辖区数据：**来自“拜占庭重置:涅槃”（Byzantium Overhaul: Nirvana，创意工坊 3602306286），经授权使用。
- **致谢：**感谢以下创意工坊模组。竹子大王的社区DLC（创意工坊 3763953914）：大元官服肖像（四档圆领袍、蒙古交领衣、蒙古帽、展脚幞头、垂翅幞头）与元廷六位人物（欧阳玄、许有壬、苏天爵、揭傒斯、泰不华、余阙）的能力估值，东罗马军队的单位模型（罗马盔、具装覆面盔、札甲、斯帕塔剑、鸢盾与扇形盾、拉布兰旗），大元军队的单位模型（护脸盔、札甲、范阳笠、绑腿、直刀与雁翎刀、虎头盾、半具装马铠）。模型与贴图照原样借用并改名，定义与挑选规则是我们自己写的，经竹子大王本人同意使用；文件清单见包内 `third_party/bamboo_king/`。下列模组给了我们结构或写法上的借鉴，脚本和文字都是我们自己写的：《The Reich / 帝国》（3823496063）——边疆定居的登记与核实、出资人的回报与赎回、战后分封（经营边区、战后安排），换地前按名单快照、只转仍归原主之地的写法与把原版立陶宛皈依包成可调用效果的写法（拉丁世界五期），“关键一块先到手、其余才做”的步骤顺序（塞尔维亚二、三期）；《Rise of the British Empire》（3621489583）——特许公司的分步解锁、两级买地、具名租让与“收归国有 / 退出”两种结局（罗马商社）；“拜占庭重置:涅槃”（3602306286）——按类别、只记不动钱的月账（军区账本）；《Basileia Romaion: 1337》（3618199037）——把地交给已定义而不在场的国家来让它复国（黑羊、白羊、伊梅列季、突厥诸侯）；《Refined Colonization》（3816832717）——商站的准入名单（招民垦荒）；满洲-清朝风味扩展（3714561641）——藩王附属类型的结构（投下宗王），朝贡觐见“按请求裁决、按对方收入计价”的事件结构与附属出兵的意愿（高丽），军粮储备的省份修正与省份粮食的读法（海运），通胀档位的写法与每月通胀的量级（钞法）；National Destinies（国家天命，3668193813）——“先选路线、再分三阶、每阶一张条件清单”的结构（大元中兴）；Praecepta Militaria - Propyrglon tou Dunabeos（3820674880）——“保护而非附庸”的单向关系的建立与撤销（塞尔维亚二、三期）；Flavorium Universalis - Rhomania（3791634667）——“丝路重开”修正的键组合与量级（中兴与霸业第三批）；MEIOU and Taxes（3735059838）——把通胀按小数读取的写法（钞法）。天朝拓展（Celestial Empire Expansion，3810799047）、Praecepta Militaria 系列、The Persianate World 和 Rhomania - a Journey To The West 的脚本注释里记下的引擎行为，帮我们查出并避开了几处问题。

制作：寐夜空灵、miscos330

---

# 凤凰计划测试版 v6.8 更新日志

- **起点：** v6.7（2026 年 11 月 20 日）。
- **终点：** 2026 年 11 月 21 日。
- **游戏版本：** 欧陆风云 5，1.4.9。

## 写在前面

- 这一版包括原定 v6.7.1 的修正（不再单独发 v6.7.1），以及军区与经济、拜占庭各线、巴尔干与拉丁世界、大元四方面的新内容，另有东罗马与大元的三套新外观。
- 事件从 1229 个增加到 1372 个，中文文本从约 17200 条增加到约 18300 条。发布包比 v6.7 大约 100 MB，主要是新外观的模型和贴图。
- **不支持旧存档：以前任何版本的存档都不能用于这一版，请新开一局。**
- **测试情况：**这一版的新内容大多只在短测试局里用测试按钮触发看过一次（事件能弹出、选项的效果能到、没有报错），没有跑过长局，自然触发的时机、电脑国家的走向和长期平衡都还没验证，所以全部按“实验性”发布。条目里写了“已在游戏里看到”的，是测试时确实看到成立的部分；写了“还没进游戏看”的，只做过离线检查。遇到问题请截图反馈。

制作：寐夜空灵、miscos330

---

## v6.8

### 军区与经济

- **军区账本。**每张军区卡片多一行“朝廷本月”：饷、属官、上缴、军区自取的税基、多少处地不出征召兵；军区页顶部一行是全体军区的合计，悬停可以看每一项怎么算。只是显示，不改任何数。已在游戏里看到：卡片这一行、页顶合计和读数，数字对得上。军区自取的税基是否从朝廷的税收里扣，还没测定，所以没算作朝廷的支出。
- **军区托管。**卡片上的“托管”按钮（或页顶“军区托管”一次全部）把军区交给将军打理：每年一月照 AI 帝国的规则改方针、改行授地、为离心多年的将军请豪族子弟接任、给边镇修堡募兵，闲着的军区自己开工程。
  - 托管的军区不再抽到军区故事、辖区故事和边患事件；叛乱预警、篡位、征伐应召和元老院表决照常弹出。托管军区遇到“授地世袭”时，替你按 AI 的答法作答。
  - 代价：军务效率 −5，花费照旧。收回随时可以，收回后 12 个月内不能再托管。只给玩家用：帝国交给电脑时，托管自动取消。
  - 已在游戏里看到：托管与收回、代价、边镇修堡和募兵、换将、闲置军区开工程、全部托管与全部收回、冷却、只给玩家。按“真到一月”自然走一轮还没看。“授地世袭”的自动作答见已知问题。
- **经营边区第四、五步。**筑堡置屯之后，档案走到“招资”：请豪族出资（国库 +200，此后 20 年每年一月付回报，前 10 年每年 24、后 10 年每年 12）、请修院出资（+150，不付回报）、请罗马商社出资、国库自筹，或无人出资。付不起的回报记作欠款，并扣帝国权威。柱石面板新行动“赎回边区股份”可以提前了结一份契约：赎价是 220 减去已付年数 × 12（最少 50），另加欠款。招资满 10 年后是“归化”：可以推行罗马化，或记功立碑，档案就此关闭。已在游戏里看到：招资的选项、年结、欠款、赎回、归化的“记功立碑”。
- **商社为边区出资。**有合股章程、本钱不少于 200 时，“招资”一步可以请罗马商社出本钱，回报付进商社的本钱；商社散伙以后这份契约作废。已在游戏里看到。
- **罗马商社第三期：坐大与结局。**合股的商社自主度到过 40 以后进入“坐大”：到 70 会自行其是，到 90 或连续两年亏空会有危机。皇帝随时可以把合股的商社收归国有（国库付本钱的一半给股东）；危机里也可以让步，或把商社交给合伙人。1360 年以后可能买下热那亚人手里希俄斯的股份；受商社保护满 10 年的统治者可能自愿成为帝国的朝贡国；连续 5 年没有京城或没有一处商站，商社散伙。已在游戏里看到：“商社自行其是”和散伙。收归国有、希俄斯的股份、受保护者称臣还没进游戏看。
- **海军军区领到军饷。**以前海军军区的军饷总额按船数算，分钱却按陆军规模分，海军军区几乎分不到；现在按船数照领。新开局的其余部分（色萨利的盗匪据点、三支佣兵、内阁、五个军区）和以前一样。已在游戏里看到。
- **军区页。**卡片改成固定宽度，边镇卡片上的按钮不再出界，账本一行不再压住上一行；换将只在真换上人时才扣 3 帝国权威；托管的边镇先看边患、再修堡（以前修堡把边患压低以后就不募兵了）；页上各个按钮的悬停提示修好了。已在游戏里看到。

### 拜占庭各线

- **中兴与霸业第二批。**柱石面板新卡“中兴之业”：可以改定一次方略（西向、东向、海上或不立方略，花 5 帝国权威；选“维持原议”不花钱，也不算用掉）。“旧疆复归”多一个选项：免费开一份经营边区的档案。帝国处在中兴以上时，塞萨洛尼基被合围、城心耗尽，不再直接交城，改由你选：死守（掷骰，守住的几率 30% 到 75%，守不住稳定度 −7）或开城议和；一局最多两次。已在游戏里看到：改定方略、“中兴”的新正文、守城掷骰的两种结果。
- **中兴与霸业第三批：九路各异（前四路）。**征伐取胜之后各有一件事：埃及（亚历山大的牧首与粮船）、意大利（罗马主教）、波斯（大不里士商路，“丝路重开”）、黑海（热那亚商站，可以交给罗马商社经营）。每月最多一件，不和本线其他事件同月。已在游戏里看到：四件事和它们按月依次到来。
- **失城之后的教会（教会线第六期）。**京城一旦不在帝国、叛军或帝国附庸的手里，各条教会线和教会合一线当月一齐收线，编年史新增一行“教会与牧首”。随后有一条通知，说明牧首区的下场：被解散、被京城的新主人留着、由别国接手，或在和约里被解散。去留由原版让京城的新主人决定，模组不改。收复京城以后这些线不会重开。已在游戏里看到：交城以后各线自己收线、通知弹出。
- **最后的围城第三期。**城破之后朝廷迁到摩里亚时（1458–1475），可能来“最后的专制公领”：守住地峡（掷骰，5% 到 60%）、补交欠贡求苏丹缓兵一次，或放弃摩里亚渡海而去。摩里亚只会因为你的选择或你自己选择去掷的骰子而丢掉。之后有“去意大利的人”（资助学者、请他们回来办学或随其自便）和“北方的婚事”（嫁去莫斯科或西方）。守住京城的局里有 1453 年的“千年之城”，以及特拉比松的求援和狄奥多罗的使者；帝国不参战。还没进游戏看。
- **长房之争与宫廷阴谋。**长房之争的新朝期间，宫廷阴谋不再开始（v6.7 的已知问题）。还没进游戏看。
- **原版事件的冲突。**1337 年开局里，原版讲静修派之争的两个事件不再发（本模组有自己的一条）；原版保加利亚、热那亚的两个事件不再把本模组的“凤凰”灾难当成“拜占庭在灾难中”，热那亚也就不会借此直接拿走希俄斯；原版“奥斯曼的崛起”事件的复制件补上了 1.4.9 的改动，不再报错；摩尔达维亚那一步过了时限仍没有摩尔达维亚时作废；“圣索菲亚的穹顶”改讲成地震的后续，卡特琳娜一段补了一句。已在游戏里看到：这四个原版事件都没有发、报错没有了、摩尔达维亚一步、两段新文字。希俄斯要等长局看。

### 巴尔干与拉丁世界

- **塞尔维亚与多瑙河防线，一至三期（1371–1444）。**只在塞尔维亚、奥斯曼、匈牙利等都由电脑控制、与帝国无关时发生；不开战，不拿玩家的地。
  - 一期（1371–1390）：南方诸侯（普里莱普的马尔科等）向苏丹称臣、拉扎尔大公迁都克鲁舍瓦茨、尼什陷落、科索沃之战。帝国一侧有“拉扎尔的使者”（暗中送钱会提高塞尔维亚在科索沃之后不称臣的几率，劝和则降低，最多 40%）和“科索沃的消息”。
  - 二期（1395–1422）：奥斯曼吞并剩下的领主国；塞尔维亚脱离奥斯曼并得十年停战；贝尔格莱德与马奇瓦归塞尔维亚、迁都贝尔格莱德，匈牙利对它是“保护”而不是附庸；吞并泽塔；事件“坎塔库泽诺斯家的新娘”。
  - 三期（1427–1444）：贝尔格莱德还给匈牙利、斯梅代雷沃成为新都、斯梅代雷沃之围（掷骰）、新布尔多、塞格德和约；事件“斯梅代雷沃的城墙”“流亡的专制公”。
  - 已在游戏里看到：三期的世界步骤和五个事件大都用测试按钮走过一遍（二期贝尔格莱德那一步要先把匈牙利的好感补上才走得到）；斯梅代雷沃守住、整国被吞并后复国这两种情形还没看。
- **电脑国家之间交地后的“安顿”。**塞尔维亚线、阿尔巴尼亚线里电脑国家之间交出的地，新主人会立刻整合、控制拉满、安抚人口。已在游戏里看到：执行无误，交出去的地都留在新主人或其附庸手里。
- **阿尔巴尼亚与斯坎德培，一期（1385–1419）。**萨夫拉之战后阿尔巴尼亚诸侯向苏丹纳岁贡；都拉斯、莱什、斯库台先后归威尼斯（威尼斯付钱给原主），阿夫洛尼亚、培拉特一带归奥斯曼。只在电脑国家之间进行，不开战，不拿玩家的地。帝国一侧有“萨夫拉的消息”“都拉斯求售”（可以抢先买下都拉斯）和“阿卡迪亚的头人”。已在游戏里看到：四个世界步骤和“萨夫拉的消息”；另两件还没看。
- **阿尔巴尼亚的同化。**罗马化运动在阿尔巴尼亚只从阿尔巴尼亚人过半的地方起步（以前可能落在希腊人的地方，同化就一直是 0）。已在游戏里看到。
- **爱琴海诸领主，一期。**1346 年维尼奥索的舰队到希俄斯：出钱守住、把收入包给股东，或让出。1355 年前后热那亚冒险家加蒂卢西奥来投：许婚封莱斯沃斯、只雇他的船，或打发走（只在第二次内战没有发生时）。1362 年前后马奥纳送来岁贡：收下、收钱不认产权，或不收而要岛。原版有一个事件会不问玩家把希俄斯等岛交给热那亚，本线第一个事件的前两个选项会挡住它。已在游戏里看到：三个事件、包税与让出、马奥纳的岁贡、加蒂卢西奥的封地；让出希俄斯以后包税修正没去掉的问题已修好并看过。
- **拉丁世界四期：教廷（1377–1442）。**教廷回到罗马（只在教廷由电脑控制时）；1439 年的“两顶红帽”（希腊人入枢机团）；合一线“两份邀请”里站在教皇一边还是巴塞尔一边，会结算教廷和萨伏依的好感与教皇的权威。已在游戏里看到。
- **拉丁世界五期：洗礼与格伦瓦尔德（1384–1423）。**事件“立陶宛的洗礼”：可以请牧首写信，争取立陶宛从东方受洗；之后的世界步骤：立陶宛从东方受洗（几率最多 20%）、托伦和约、萨莫吉蒂亚受洗、梅尔诺和约。只在立陶宛、波兰、条顿骑士团都由电脑控制时发生，不碰帝国的地。已在游戏里看到：事件、东方受洗、托伦和约的两种结局、后两步；“立陶宛仍是异教”那一支要另开一局看。

### 大元

- **钞法（一期）。**钞信 0–100 分四档，影响通胀；“变钞之议”（至正十年）、每年的岁用之议、“钞法大坏”、“收钞复信”。已在游戏里看到：“变钞之议”和它带来的通胀，以及钞法和海运的联动。
- **海运与京仓（一期）。**京仓存粮分档，每年五月按几项来源结算；京畿屯田；六个事件（如“京师大饥”）。已在游戏里看到：“京师大饥”，以及钞法跌到低档时它的选项随之改变。
- **大元中兴（一期）。**1355–1372 年间由四种缘由开启“中兴之议”：汉法更化、祖述国俗，或暂缓；第一阶段“安内”有一张条件清单和“受挫”的压力，可以失败。只给大元发事件，不开战、不换地。已在游戏里看到：“中兴之议”和第一阶段的清单。
- **高丽（一期）：册封与贡献。**每月算高丽的“向背”；“高丽请命”（请封、请婚、请罢贡女、请赐）；人玩高丽时可以遣使；奇氏贵盛（1353–1355）；平乱时向高丽征兵。1356 年的决裂只记下来，留给二期。已在游戏里看到：“高丽请命”和为三期备好的叛军。
- **1340 年的储君。**“撤文宗庙主”：照《元史》，燕帖古思被禁继位、流放途中病逝，立皇子爱猷识理达腊为皇太子；也可以把燕帖古思留在朝中。已在游戏里看到。
- **投下宗王。**十位藩王的附属类型改成“投下宗王”（不能被吞并、随大元打防御战，档位按诸王线的忠诚）；八位王的投下食邑（照《元史》卷九十五）与“食邑陷没”；1339 年金帐汗国的使者；辽阳牵制东道诸王；梁王杀段功一事改成“一说”，并加“梁段复和”一步。已在游戏里看到：类型切换、“食邑陷没”。其余几件还没看。
- **土司第三轮。**滇西南五个直属土司和麓川、孟连改挂梁王名下；七个第三层小土司并入上级；思州、丽江拆回 15 处地以内，保持土司身份。大元直属的附属国从 69 个减到 62 个。已在游戏里看到：各项计数全对。
- 哈密开局改归豳王（史载出伯一系世守肃、瓜、沙、哈密一线）；还没进游戏看。
- **六位元廷人物。**1337 年开局新增欧阳玄、许有壬、苏天爵、揭傒斯、泰不华、余阙。已在游戏里看到：其中五位（许有壬在名单下方没翻到）。
- **修正。**诸王线“上都朝会”读了未设置的变量、几个大元事件的音效类型写错，加载和显示时都会报错；都修好了。已在游戏里看到。

### 外观

- **东罗马军队：**罗马盔、具装覆面盔、札甲、斯帕塔剑、鸢盾与扇形盾、拉布兰旗。只给拜占庭本国，管 1337–1437 年两个时代，之后回到原版外观；附属国不变。
- **大元官服肖像：**四档圆领袍、蒙古交领衣、蒙古帽、展脚幞头、垂翅幞头，给大元的皇帝、诸王、朝臣和行省长官；别国不变。
- **大元军队：**护脸盔、札甲、范阳笠、绑腿、直刀与雁翎刀、虎头盾、半具装马铠；给大元、行省、宗王和北元；别国不变。
- 三套都来自“竹子大王的社区DLC”，经竹子大王本人同意使用（见致谢）。已在游戏里看到：都能正常显示。马铠贴不贴合、部队多时的帧率还没细看。

### 修正

- 经营边区“在边地修一座堡垒”实际要扣约 379 金（文字写 150，游戏另收了城堡的造价）；现在只扣 150 金。已在游戏里看到。
- “希罗基蒂亚之败”换成原版事件用的配图（原来是空框）；瓦尔纳一战换了配图。还没进游戏看。
- 译名：“塞雷”“塞雷斯”统一为“塞莱”，“塞利姆布里亚”“塞林布里亚”统一为“锡林布里亚”，“加提卢西奥”改为“加蒂卢西奥”，英文的 Maona 统一。小亚细亚和色雷斯的 45 个省名以前对所有国家都换成了希腊语名，现在只对宫廷语言是希腊语的国家生效：玩奥斯曼、突厥诸侯、马穆鲁克等时显示游戏原名（拜占庭看不出变化）。“加蒂卢西奥”已在游戏里看到，其余还没看。
- 从每月人力算的 28 处花费加了“不小于 0”的保护；专制公外交、军区点兵的罚金、元老院表决三处写法改得更稳，行为不变。还没进游戏看。
- 性能：军区辖区的判断和账本的计算改成更省的写法。还没测帧时间。
- 又修了一轮小错（还没进游戏看）：合一线的一条报错、塞尔维亚外交界面缺的两句说明；招安、商社散伙、中兴“亚历山大与粮船”、合一线“两份邀请”的提示文字补全；大元面板和罗马世界面板的按钮补上悬停说明；大元“中兴之议”的长提示拆成多行；大元灭亡时钞法线也随之收束。

### v6.7 的内容在游戏里补看到的

- 军区自行补员补出的团确实加进了军区的军队（比扣费晚几天到）；“按建议设置”真的改了方针并扣了帝国权威；“边镇一齐”；普罗尼亚授地灰显并写明原因；商社买地、年结、保护约订成；最后的围城第二期的三件事；中兴与霸业第一批的三个事件；元末平乱的“招安”与“贾鲁治河”。

---

## 已知问题

- 这一版的新内容只在短测试局里看过，没有跑过长局；v6.5 以来的内容也大半没有经过完整的游戏内测试，全部按“实验性”发布。
- 旧存档不支持，请新开一局。
- 开局头 20 天，东正教农民会减少约 6.1 万人，原因还在查。
- 开局几周内可能出现“拜占庭对艾登保障独立”。本 MOD 和原版都没有替玩家做这个决定的脚本，最可能是艾登按原版规则请求保障、被接受了，还在核实。
- 托管军区的“授地世袭”自动作答在测试局里还没看到成立（授地月数在月初被清零），原因还在查。
- 京城的新主人可能解散普世牧首区（原版让新主人决定去留，和约里也可能解散）；京城一失，教会各线就一齐收线（教会线第六期）。
- 大元的建筑式行省可能加入原版的独立运动（测试局里见过河南江北行省加入），是否应当如此还在查。
- 大元“行省与诸王”面板的九行摘要卡还没在游戏里看过。
- 拜占庭部队外观在日志里有两类警告（罗马头盔多余的贴图通道、重步兵盾牌挂载缺默认项），不影响显示。
- 军区（建筑型国家）不能自己招正规军：这是原版规则，原版的汉萨同盟也一样。
- 中文的右括号偶尔会落到行首，这是游戏换行规则造成的。
- 少数原有文件在加载或运行时有提示，不影响游戏。

## 兼容性

- 只适配游戏版本 1.4.9。
- 不支持旧存档：以前任何版本的存档都不能用于这一版，请新开一局。
- MOD 改写了 1337 年开局的部分原版文件（国家、建筑、外交、国际组织、地区偏好）和几份原版事件文件（拜占庭、保加利亚、热那亚、塞尔维亚、奥斯曼的崛起等）。改同一批原版文件的模组大多不兼容，不建议同时启用。

## 借鉴与致谢

- **按许可集成：**国家、文化、王朝等的历史介绍文字来自“描述扩展：国家、文化、王朝及更多”（Descriptions Expanded，[创意工坊 3838927963](https://steamcommunity.com/sharedfiles/filedetails/?id=3838927963)），© Descriptions Expanded contributors，按 CC BY-SA 4.0 使用。凤凰计划在其基础上为自有的国家和家族补写了条目，并让两处文本与本 MOD 的原文合并；这些增补同样按 CC BY-SA 4.0 提供。详见包内 `third_party/descriptions_expanded/`。原许可、署名、来源清单和改动说明都在这个文件夹里。
- **军区辖区数据：**来自“拜占庭重置:涅槃”（Byzantium Overhaul: Nirvana，创意工坊 3602306286），经授权使用。
- **致谢：**感谢以下创意工坊模组。竹子大王的社区DLC（创意工坊 3763953914）：大元官服肖像（四档圆领袍、蒙古交领衣、蒙古帽、展脚幞头、垂翅幞头）与元廷六位人物（欧阳玄、许有壬、苏天爵、揭傒斯、泰不华、余阙）的能力估值，东罗马军队的单位模型（罗马盔、具装覆面盔、札甲、斯帕塔剑、鸢盾与扇形盾、拉布兰旗），大元军队的单位模型（护脸盔、札甲、范阳笠、绑腿、直刀与雁翎刀、虎头盾、半具装马铠）。模型与贴图照原样借用并改名，定义与挑选规则是我们自己写的，经竹子大王本人同意使用；文件清单见包内 `third_party/bamboo_king/`。下列模组给了我们结构或写法上的借鉴，脚本和文字都是我们自己写的：《The Reich / 帝国》（3823496063）——边疆定居的登记与核实、出资人的回报与赎回、战后分封（经营边区、战后安排），换地前按名单快照、只转仍归原主之地的写法与把原版立陶宛皈依包成可调用效果的写法（拉丁世界五期），“关键一块先到手、其余才做”的步骤顺序（塞尔维亚二、三期）；《Rise of the British Empire》（3621489583）——特许公司的分步解锁、两级买地、具名租让与“收归国有 / 退出”两种结局（罗马商社）；“拜占庭重置:涅槃”（3602306286）——按类别、只记不动钱的月账（军区账本）；《Basileia Romaion: 1337》（3618199037）——把地交给已定义而不在场的国家来让它复国（黑羊、白羊、伊梅列季、突厥诸侯）；《Refined Colonization》（3816832717）——商站的准入名单（招民垦荒）；满洲-清朝风味扩展（3714561641）——藩王附属类型的结构（投下宗王），朝贡觐见“按请求裁决、按对方收入计价”的事件结构与附属出兵的意愿（高丽），军粮储备的省份修正与省份粮食的读法（海运），通胀档位的写法与每月通胀的量级（钞法）；National Destinies（国家天命，3668193813）——“先选路线、再分三阶、每阶一张条件清单”的结构（大元中兴）；Praecepta Militaria - Propyrglon tou Dunabeos（3820674880）——“保护而非附庸”的单向关系的建立与撤销（塞尔维亚二、三期）；Flavorium Universalis - Rhomania（3791634667）——“丝路重开”修正的键组合与量级（中兴与霸业第三批）；MEIOU and Taxes（3735059838）——把通胀按小数读取的写法（钞法）。天朝拓展（Celestial Empire Expansion，3810799047）、Praecepta Militaria 系列、The Persianate World 和 Rhomania - a Journey To The West 的脚本注释里记下的引擎行为，帮我们查出并避开了几处问题。

制作：寐夜空灵、miscos330

---

# 凤凰计划测试版 v6.7 更新日志

- **起点：** v6.4（2026 年 11 月 19 日）。
- **终点：** 2026 年 11 月 20 日。
- **游戏版本：** 欧陆风云 5，1.4.9。

## 写在前面

- 这一版合并了 v6.5、v6.6、v6.7 三版的内容，下面仍分三段写。
- 故事从 1347 年的黑死病铺到 15 世纪后半：黑死病与色雷斯、长房之争、最后的围城、中兴与霸业；周边的克里米亚、拉丁希腊、格鲁吉亚、伊尔汗国的继承者；制度上有军区自行补员、罗马商社、战后安排与经营边区。
- 事件从 1082 个增加到 1229 个，中文文本从约 13600 条增加到约 17200 条。
- **这三版的新内容大半只做过离线检查和冒烟测试，没有经过完整的游戏内测试，全部按“实验性”发布。**条目里写了“已在游戏里看到”的，是测试时确实看到成立的部分。遇到问题请截图反馈。
- **旧存档：**读旧存档没有测过，建议新开一局。

制作：寐夜空灵、miscos330

---

## v6.7

本版的大部分内容是新的故事线和新玩法，按惯例标为实验性内容，遇到问题请截图反馈。

### 主线

- **黑死病与色雷斯（1347–1371）。**新的一条线，从瘟疫传到君士坦丁堡写起：朝廷怎样应对第一波瘟疫、皇帝往布达去求援、阿德里安堡守城战。之后还有空屋里迁来的新户、迪迪莫泰洪、塞尔维亚专制公的求援，以及每隔十年左右可能卷土重来的瘟疫（最多四次）。
  - 阿德里安堡守城：你可以选择倾力守城，按显示的胜算掷骰；守不住时城会归奥斯曼苏丹。这一事件已经在游戏里看到过：事件有配图、三个选项，守城失败后城确实交给了奥斯曼。
  - 色雷斯的城只会因为你自己的选择或你自己选择去掷的骰子而丢掉；周边世界的变化不会拿走玩家的土地。
  - 阿德里安堡失陷的年份，正文写作“1369 年前后（旧说早到 1361 年）”，按日期给出不同版本的正文。
- **长房之争（约 1390 年）。**约翰七世一系与在位皇帝之间的争执：锡林布里亚的怨望、金门、罗得岛的战船；之后苏丹开出的价钱、“另一位皇帝”、叔侄能否和解。皇位只会因为你的选择或你自己选择去掷的骰子而易手；共治皇帝沿用模组原有的做法。
  - 这条线已经和教会线（1390 年换牧首）、塞萨洛尼基线、1399 年皇帝西行时的留守人接上；和宫廷阴谋之间的衔接这次没有接，所以新朝的头几个月里宫廷阴谋仍可能开始。
- **最后的围城（1440–1480 之间，由局势触发）。**不按日期：只有帝国真的衰弱时（奥斯曼兵力远超帝国、已占埃迪尔内并与京城接壤等条件同时满足），苏丹才会来围君士坦丁堡。你可以守城（掷骰，守住的几率随局势和准备在 5% 到 75% 之间）、开城、花钱买和或拖延。不打真实战役，京城只会因为你自己的选择或你选择去掷的骰子而丢掉。
  - 围城前可以请热那亚人守陆墙、皇帝亲守陆墙或把修士和市民编进城防，各自提高守城几率。
  - 如果京城失守而帝国还有别的领土（比如摩里亚），朝廷会在新首都重新立足：号召各地、立誓光复或先求苏丹承认；随后还有阿尔巴尼亚人起事和苏丹的贡金。拖欠贡金不会直接引发战争。
  - 帝国被整个吞并以后，模组的故事就不再运行，所以“城破之后”的内容只在帝国还留着地的局里出现。
  - “先迁都、再交出京城、再停战”这一步已在游戏里看到成立（1337 年的测试局里，京城归了奥斯曼，首都迁到卡尔西顿）。
- **中兴与霸业（强势路线）。**给打得好的帝国一条统一的“强”的标准：每年一月按帝国一方握有的历史辖区数评定“立足—中兴—霸业—光复”几档，达到时弹出事件，可以选威望、稳定、帝国权威等奖励；之后是“旧疆八阶”，每收回一片旧疆给一次奖励（给帝国自己已经拥有的地加核心，或加帝国权威等）。这条线本身不拿地、不宣战。辖区计数已在游戏里看到：1337 年开局握有 6 个辖区，8 个进“立足”，15 个进“中兴”。

### 周边世界

- **拉丁希腊“晚景”（1383–1446）。**纳克索斯、内格罗蓬特、亚该亚的易主；帝国这边有“被俘的代理人”（收赎金、以人换地或无偿放人）和 1444 年前后“底比斯的归顺”（进兵收雅典为附属、只收岁贡或守住地峡）。
- **伊尔汗国的继承者 第三期“波斯腹地”。**克尔曼、设拉子、沙赫·舒贾、赫拉特一带的变化，都只在相关国家都是电脑控制、与帝国无关时发生，不开战。
- **元末平乱 第三期全部做完。**孛罗起事、入京秉政与如何处置孛罗；封河南王、关中诸将拒命、大抚军院、追复脱脱；最后是大都与尾声，元末平乱这条线到此全部完成。
  - 孛罗入京后会先腾出一个内阁席位再入阁；这一处已在游戏里看到成立。
- **意大利特权 第四期“小共和国”。**拉古萨的金玺诏书、比萨人的旧宅；比萨不在而佛罗伦萨占着比萨城时，比萨的特权改由佛罗伦萨承接。塞萨洛尼基交给威尼斯时，可以抵掉一部分威尼斯的索赔。
- **拉丁世界 第三期“两位教皇与求援”。**西方大分裂期间的两位教皇、分裂结束；新的行动“遣使罗马求援”，教皇会给出答复，可能组织十字军。
- 东地中海、格鲁吉亚、伊尔汗、克里米亚、拉丁希腊各条线的事件正文里，人物现在只写名字，不再出现“公爵某某某某”这样读着别扭的全名。

### 制度与界面

- **军区自行补员。**军区每年一月会按定额自己补兵：陆军军区补步兵团，海军军区补桨帆船，花费按财制分摊；军区忠诚低于 40 时停止补员。军区卡片上多了一格“兵 现有/定额”，军区页有一句汇总，“军区经营”里有总开关。已经在面板里给军区设了目标的，仍按原来的面板来。停补的条件和补员时的扣费已在游戏里看到；补出来的团是否真的加进了军区的军队，还没有看到。
- **军区页整理。**页顶新增“按建议设置”和“边镇一齐”两个按钮；手动补充兵力收进默认收起的“加急”一组；普罗尼亚授地在法律不允许时显示灰色选项并写明原因；塞萨洛尼基相关正文里的“专制公”改称“守臣”。
- **罗马商社（假设性玩法）。**历史上拜占庭没有这种特许商社，这是参照热那亚人在希俄斯的马奥纳和威尼斯的定期船队设想出来的玩法。你可以给商社颁发章程（皇室专营、君士坦丁堡商人、热那亚或威尼斯合伙人），每年对一次账，商社与国库分账；柱石面板“商社”一组有“注资”“查账”两个行动；股东会提出请求。商社的据点就是黑海商站。
- **商社置地与保护约。**章程满十年、商站有了规模之后，商社可以向别国求买商站旁的地或城里的街区（对方自己答应才成交，回绝时退一半价钱），也可以和弱小的港口主人订保护约（商社每年付费，最多三个）。海外商站的站址增加法马古斯塔、亚历山大、贝鲁特三处，上限从 4 处提到 6 处，原来的“黑海商站”修正改叫“海外商站”。“过户并停战”一步已在游戏里看到成立：买来的地成了殖民城。
- **罗马殖民城。**黑海商站所在的地方归帝国自己以后，可以设为殖民城。
- **战后安排。**帝国整个吞并一个较大的国家（公国以上、6 处地以上、首都在历史辖区内）后，下个月会弹出事件，让你决定旧都一带留作直辖、其余地方设军区、封宗室专制公、立本地专制公为罗马盟邦，或全部直辖；再决定旧王的去处。
- **经营边区。**柱石面板“边防与兵员”一组新增行动“经营边区”（3 帝国权威、100 金）：在帝国已有至少三处地、其中有荒地或新近得来之地的历史辖区开一份档案，依次立籍（两年，战时不计）、招民、筑堡置屯（修城堡、安置兵户、授普罗尼亚等）。同时最多三份，战事到了该辖区就停表；只动帝国自己的地。开档和修城堡已在游戏里看到成立，其余步骤还没看。
- 模组现在会识别“本局是否从 1337 年开局”，只有 1337 年开局的局里才运行模组的主线故事。新开的 1337 局里已看到主线照常运行；读旧存档的情况还没测。

### 修正

- 拉丁希腊三位新君主在任何年份建出来都是成年人。
- 元末平乱里提前建出的人物如果还未成年，会按成年人建出，避免被内阁拒绝；这一处已在游戏里看到成立。

---

## v6.6

### 主线

- **教会合一 第二至第四期。**以弗所的马可、没有加冕礼、罗马的条件、圣索菲亚的礼拜；合一生效期间换皇帝、废合一时换牧首都有相应处理；之后是金玺诏书、宫中的辩论、去佛罗伦萨教希腊文、康斯坦茨的希腊人、教皇的答复。
- **教会 第四、五期。**1368 年的会议；修院地产（一半修院地产、修院要回田产、圣山的新主人），修院地产分四个等级，各有效果；随机发生的教会小事件；莫斯科拒绝合一、罗斯自选都主教。
  - 注意：修院地产“豁免”等级的效果（教士满意度目标 +5%、税收效率 −3%）对所有新局都生效，包括不碰教会事件的局。

### 周边世界

- **突厥诸侯 第二、三期。**苏丹索要费拉德尔菲亚、卡拉曼的使者、帖木儿的恩典；艾登等诸侯成为奥斯曼的附庸，1402 年后解除附庸并可能复建被吞并的诸侯；卡拉曼的密约、盖尔米扬的遗嘱。“卡拉曼的密约”和遗嘱一步已在游戏里看到。
- **东地中海与多瑙河 第二、三期。**瓦拉几亚与塞浦路斯：希罗基蒂亚之败、法马古斯塔归还、“摩里亚的新娘”（公主真的嫁到塞浦路斯）等。“希罗基蒂亚”事件已在游戏里看到，但目前没有配图。
- **安纳托利亚地区小事件。**马拉蒂亚易主、埃雷特纳称苏丹等四个周边变化，以及一个只给玩埃雷特纳的玩家的事件。
- **克里米亚 第一至第四期。**索尔代亚易手、哥特亚海岸、索尔哈特之战、狄奥多罗的毁与重建、特拉比松联姻、琴巴洛之战；之后是瘟疫船、银行与苏丹的舰队、卡法和曼古普陷落（到 1476 年）。帝国一侧有若干事件。地图上卡法、索尔代亚、索尔哈特三处改用这些中文名。卡法、曼古普两步和索尔代亚易手的事件等已在游戏里看到。
- **拉丁希腊 第一至第三期。**底比斯遭劫、纳瓦拉兵团进亚该亚、阿恰约利入主雅典、内里奥的遗嘱（帝国可以出钱买下科林斯）；杜尚南下到阿尔塔换主，色萨利、伊庇鲁斯、约阿尼纳三个国家；萨洛纳的伯爵夫人、约阿尼纳开城，到阿尔塔陷落。伊庇鲁斯从被吞并到复国、换主的七步，和“内里奥的遗嘱”已在游戏里看到。
- **格鲁吉亚 第一至第四期（到 1466 年）。**特拉比松的婚约、第比利斯陷落、国王归来；伊维隆的两个修团、不肯签字的主教、使者东行、送亲的船；西部自立、卡赫季、伊梅列季的王冠、帕拉瓦尼湖。第二至第四期的大部分步骤和两个事件已在游戏里看到。
- **伊尔汗国的继承者 第一、二期。**木撒汗的结局、大不里士的西方商人、黑羊与白羊建国、白羊的新娘；札尼别南下、大不里士易主、帖木儿的使者、海峡的渡口等。黑羊、白羊建国和札尼别南下等已在游戏里看到；与帖木儿本人有关的部分 1337 年开局测不到。
- **黑海粮道。**粮道分通畅、吃紧、断绝三档，吃紧或断绝时全国食物和市民满意度下降；京城缺粮、黑海粮约，以及新行动“包租粮船”。
- **黑海商站。**新的外国建筑“罗马商馆”：向对方请求开设，对方准许或拒绝；之后有商站被扣、商站兴旺等事件，开设和关闭两个行动，每年有维持费。商馆建筑和“商站失陷”事件已在游戏里看到。
- **招民垦荒 第二期。**塞萨利的阿尔巴尼亚牧人、草原来的逃人、伯罗奔尼撒的阿尔巴尼亚人、兵户的儿子。
- **意大利特权 第二期。**新行动“向意大利人买船”；意大利人的船队、两大共和国交战、威尼斯的索赔、讨价还价；还清借款或破产会影响好感。“买船”已在游戏里看到成立。
- **大元：元末平乱 第二期与第三期前两批。**汴梁之役、益都之变（察罕帖木儿遇刺）；孛罗起事、入京秉政；“将帅坐大”分一到三份。孛罗的三个事件和“将帅坐大”的增减已在游戏里看到。
- **大元：豳王。**新增第十位藩王豳王（沙州一带），列入大元面板的诸王一栏，有自己的事件。

### 制度与界面

- 编年史页新增格鲁吉亚、伊尔汗国的继承者、伊庇鲁斯与色萨利、克里米亚等多行。
- 希腊语地名：恢复了此前缺失的约 590 个原版希腊语地名，模组自己起的名字保留。已看了两处，显示正常。
- 介绍文本新增一批自有文化和国家的介绍，并订正多处史实和译名（例如李思齐条目重写、“巴列奥略”统一写法）。

### 修正

- 统一了多处中文译名：尼基福罗斯、凯法洛尼亚、西缅、普雷柳比奇、门泰谢、詹达尔、雨果四世等，与游戏里的写法一致。
- 模组里一处缺失的定义补上，加载时不再多一条报错。

---

## v6.5

### 主线

- AI 控制拜占庭时，安德罗尼科斯三世在世期间更可能加冕约翰五世为共治皇帝，让 1341 年内战更常按史实展开（不强制）。
- 修复：内战期间叛军一方也会跑一遍拜占庭的每月故事，导致部分故事重复开始（例如教会合一线反复从头开始）。

### 制度与界面

- **治绩：**军区平均忠诚、财政连续盈余且无债、宫廷七职基本在任、元老院近期表决通过——每满足一项，每季度增加少量帝国权威。已在游戏里看到：一次结算达成三项，帝国权威 +0.45。
- **以正统固权：**新行动，用正统性换帝国权威（10 换 2，冷却 2 年，正统性不低于 60 才能用）。换取的效果已在游戏里看到（那次测试是直接执行效果，没有经过门槛；门槛写在行动的条件里）。
- **民心所向：**民意连续 12 个月不低于 53 时生效，元老院每席 +5，部分军区故事的好结果更容易出现。提示已在游戏里看到“生效中”。
- **军区忠诚分项：**军区卡片的提示里列出忠诚目标值的 15 个分项，总和不变。已在游戏里看到。
- **大元面板：**在原版“中原王朝”面板里新增“行省与诸王”一页，列出九个行省和诸位藩王，有岁赐按钮；新增地图模式“行省与诸王”。面板已在游戏里看到；之后改窄了诸王列表、加粗了王号，地图模式也调整过，这些改动还没复看。
- **称谓：**大元行省长官显示“平章政事”（不再是“某某公爵”），九位藩王显示各自的王号，土司显示“土司”，大理作附庸时显示“总管”；罗马边疆领显示“督军”，远征军显示“全权将军”；罗马附属国不再一律显示“国王”，改为各国自己的称谓，希腊文化、王国以下的君主国显示“专制公”。河南江北行省“平章政事”已在游戏里看到。
- **历史介绍：**国家、文化、王朝等的浮窗底部加一段历史介绍，来自“描述扩展”（见致谢）；凤凰计划为大元九个行省、鲁王、赵王、塞萨洛尼基、金角湾和四个家族补写了自己的条目。

### 修正

- 从已知问题里删除“开局国库多 417 金”：这是游戏把开局设定的金额加在底数上，不是多出来的钱。

---

---

## 已知问题

- v6.5 以来的新内容大半只做过离线检查和冒烟测试，没有经过完整的游戏内测试，全部按“实验性”发布。
- 读旧存档没有测过，建议新开一局。
- 开局头 20 天，东正教农民会减少约 6.1 万人，原因还在查。
- 最后的围城：京城交出去几天后，游戏会自己解散君士坦丁堡普世牧首区；教会相关的故事线此后可能不正常，下一版处理。
- 军区自行补员：扣费已在游戏里看到，补出来的团是否真的加进了军区的军队还没有确认。
- 长房之争和宫廷阴谋之间没有衔接：新朝的头几个月里宫廷阴谋仍可能开始。
- “希罗基蒂亚之败”事件没有配图。
- 军区（建筑型国家）不能自己招正规军：这是原版规则，原版的汉萨同盟也一样。
- 中文的右括号偶尔会落到行首，这是游戏换行规则造成的。
- 少数原有文件在加载或运行时有提示，不影响游戏。

## 兼容性

本模组改动了 1337 年开局、拜占庭的政体与法律、称谓表、国名规则和多处原版界面。其他拜占庭整体改版、改动 1337 开局或同一批地区的模组，未做兼容，不建议同时启用。

工坊上的“凤凰计划 / 涅槃1176 兼容补丁”由其他人维护，对应的是 2026 年 10 月的版本，与当前版本不匹配；更新情况请看该条目自己的页面。

## 借鉴与致谢

- **按许可集成：**国家、文化、王朝等的历史介绍文字来自“描述扩展：国家、文化、王朝及更多”（Descriptions Expanded，创意工坊 3838927963），© Descriptions Expanded contributors，按 CC BY-SA 4.0 使用。凤凰计划在其基础上为自有的国家和家族补写了条目，并让两处文本与本模组的原文合并；这些增补同样按 CC BY-SA 4.0 提供。原许可、署名、来源清单和改动说明见模组包内的 `third_party/descriptions_expanded/`。
- **借鉴思路：**感谢创意工坊模组《The Reich / 帝国》和《Rise of the British Empire》：前者的边疆移民定居和战后分封启发了本模组“边疆经营”与“战后安排”的思路，后者的特许公司启发了“罗马商社”的思路。这一版只借鉴了机制上的想法，没有使用这两个模组的脚本或文字。

制作：寐夜空灵、miscos330

---

# 凤凰计划测试版 v6.4 更新日志

- **起点：** v6.0（2026 年 11 月 18 日）。
- **终点：** 2026 年 11 月 19 日。
- **游戏版本：** 欧陆风云 5，1.4.9。

## 写在前面

- 这一版把拜占庭的故事从 1337 年一直铺到 15 世纪中叶：新增两场内战、臣属苏丹、空位期、巴耶济德封锁，教会与合一，十字军与意大利商业，以及大元的行省、诸王和元末平乱。
- 事件从 818 个增加到 1082 个，中文文本从约 10500 条增加到约 13600 条。
- **旧存档不兼容。** 请开新档。
- 标“实验性”的内容只做过冒烟测试，或者还没在长局里自然触发过，欢迎反馈。

---

## 一、稳定性与适配

- **适配 1.4.9。** 10 处整文件覆盖原版的地方改为按原版文件生成、只改需要的部分，游戏更新后更不容易出问题。
- **国名修正：**
  - 军区、行省、边疆领、总督区等国名不再重复等级名。以前会显示成“马其顿军区军区”，英文会出现 “Theme of Theme of Macedonia”。
  - 神圣罗马帝国、尼德兰王国、瓦拉几亚保护领、匈牙利自治领、北非远征军等附庸的国名也一并修正。
- **报错清理：**
  - 修正一批会让条件失效的写法，例如国家已灭亡时仍被当作存在、几处时间条件形同虚设；
  - 修正悬停提示时刷报错的问题，例如“主持圣主教会议”的提示。
- **英文文本：**清理 23 个重复的英文文本键。以前几处事件的英文标题会显示成另一件旧事件的标题。
- **长局验证：**用观察者模式从 1337 年跑到 1411 年，没有崩溃或卡死，内存稳定。
- **内战结局不再引发连锁内战。** MOD 自己的内战结局换皇帝时，不会再立刻触发“旧王朝复辟”内战，也不会随后引发军区独立。

## 二、拜占庭主线

- **第二次内战（1352 年起）：** 21 个事件，配有局势。约翰五世与马修·坎塔库泽诺斯之争，有两种开局方式和多种结局。
- **主线调度：** 各条主线共用一把“主线锁”，每月最多一条主线大事件，避免同一个月里弹出一堆事件。
- **臣属苏丹（1371–1381，实验性）：** 21 个事件。向苏丹称臣、纳贡、出兵，同谋、越狱与篡位；刺瞎分两档。
- **空位期（1402–1413，实验性）：** 10 个事件。巴耶济德的儿子们争位，拜占庭可以押宝。新增一套通用的“押宝”框架。
- **巴耶济德封锁、尼科波利斯与西行（1394–1402）：** 京城被围时的粮食与士气，西方援军，皇帝西行求援。
- **塞萨洛尼基与穆斯塔法之乱：** 塞萨洛尼基的命运（1382–1387、1423），1421–1424 年的穆斯塔法之乱。
- **特拉比松的皇女（1340–1349）：** 伊琳娜、特拉比松内乱、阿莱克修斯三世回国即位。
- **专制公头衔外交（实验性）：** 把“专制公”尊号授给外国君主，例如 1402 年的斯特凡·拉扎列维奇。
- **摩里亚专制公国（实验性）：** 宗室出任专制公，修建六英里长城，骑士团与摩里亚的往来。
- **地区事件（1337–1341，实验性）：** 1337 年奇里乞亚和约、穆扎卡家族等。

## 三、教会

- **教会框架：**
  - 静修派、理性派、亲合一派三派份额；
  - 牧首与牧首派别；
  - 新行动“主持圣主教会议”，在三派之间作出裁断；
  - 1347 年二月的会议、布拉赫奈的会议。
- **教会一期（实验性）：** 1375 年与塞尔维亚教会和解，1393 年特尔诺沃并入普世牧首区。
- **都主教与募捐（实验性）：** 罗斯、立陶宛、瓦拉几亚、摩尔达维亚的都主教人选；向罗斯求援募捐。
- **教会合一一期（实验性）：** 佛罗伦萨会议、签字与回京后的反应。合一线运行后，原版的“佛罗伦萨会议”事件不再随机触发，改由本线安排。

## 四、拉丁世界、黑海与东地中海

- **东方十字军一、二期：** 士麦那十字军（1344）、亚历山大之劫（1365）、萨伏依的阿马德乌斯（1366）、尼科波利斯（1396）、士麦那陷落（1402）、瓦尔纳（1444）、罗得岛之围；医院骑士团接手摩里亚。
- **意大利商业特权（实验性）：** 威尼斯、热那亚、比萨、拉古萨各分三级特权。帝国柱石新增“商约与特权”一组行动：续约、借款、抵押租让。
- **东地中海与多瑙河：** 瓦拉几亚守住罗维纳、塞浦路斯的彼得一世、法马古斯塔。
- **突厥诸侯：** 艾登的乌穆尔、黑海同行、海峡之争等，配合原版的诸侯国。
- **金帐汗国（1337–1380）：** 遣使萨莱、汗国大乱、顿河之战、脱脱迷失。
- **保加利亚、摩尔达维亚与奇里乞亚：** 保加利亚的分裂与灭亡，摩尔达维亚建国，奇里乞亚 1375 年灭亡。

## 五、疆域与经济

- **招民垦荒：** 新行动，把人口迁往荒地；尼科米底亚陷落后可以接纳难民。
- **开局财政：** 开局国库调整，新增“节用”，前 24 个月每月有额外收入。
- **军区：** 换王朝后军区更稳定，不会因为换代而集体离心。

## 六、大元

- **行省（实验性）：** 内地六行省可以任免长官，忠诚分档并影响征兵与税收；新增岭北、辽阳、甘肃三个边地行省。行省国名显示为“甘肃行省”等。
- **征东行省与宣政院：** 1340 年奇氏立后、征东行省、宣政院与吐蕃。
- **大元诸王：** 九位藩王显示王号：齐王、济南王、辽王、广宁王、阳翟王、云南王（1355 年进封梁王）、沈王、鲁王、赵王。新增岁赐、忠诚和上都朝会，以及 6 个诸王事件。
- **元末平乱一期：** 红巾起事后的招安与征讨、脱脱当政、高邮之役。
- **元亡后的清理（实验性）：** 大元灭亡时，行省和诸王的状态随之收尾。

## 七、界面与文本

- **编年史页：** 帝国柱石新增“编年史”页签，28 条主线的进展一页看全。
- **元老院投票预览：** 表决前先看各派的赞成与反对票。
- **帝国柱石：** 行动分三栏，可以折叠；新增岁币与停战卡、授予尊号。
- **文本：** 统一文本格式，提示里的数值和概念加上颜色与链接；英文文本全面审读。

## 八、已知问题与实验性内容

- **实验性内容：** 臣属苏丹、空位期、专制公头衔外交、摩里亚、地区事件、教会一期、都主教、教会合一、意大利特权、大元行省与元亡清理。它们只做过冒烟测试，或者还没在长局里自然触发过。
- **已知问题：**
  - 开局国库比预期多约 417 金，来源还在查。
  - 军区（建筑型国家）不能自己招正规军：这是原版规则，原版的汉萨同盟也一样。
  - 中文的右括号偶尔会落到行首，这是游戏换行规则造成的。
  - 少数原有文件在加载时有提示（不影响游戏）。

## 致谢

- 制作：寐夜空灵、miscos330
- 军区辖区数据参考 Byzantium Overhaul: Nirvana。

---

# 凤凰计划测试版 v6.0 更新日志

- **起点：** 2026 年 11 月 17 日的版本。
- **终点：** 2026 年 11 月 18 日。
- **游戏版本：** 欧陆风云 5，1.4.7。

## 写在前面

- 这一版改动很大：重做了军区，加了疆域与附庸体系，按史实还原了 1337 年开局，补了大量历史剧情。
- **旧存档不兼容。** 请开新档。
- 内容来自两天的集中制作，大部分做过游戏内测试；没测到的放在第十节“已知问题与实验性内容”。

---

## 一、稳定性与报错

- **加载报错清理。** 修掉以下问题：
  - 覆盖原版的开局与战斗效果，导致原版效果失效；
  - 旧版地图数据副本；
  - 重复定义和语法错误；
  - 读取不存在的变量。
- **运行期报错清零。** 用观察者模式从 1337 年跑到 1341 年，跑了两轮，MOD 相关的运行期报错从 3128 条降到 0。
- **暂时关闭两套未完成的系统：**“革命的钟声”局势和“东罗马大革命”灾难。
- **文本补全：**
  - 补了 236 个事件的结果说明和 59 个隐藏事件的标题；
  - 补了 352 个缺失的中文文本，改正 16 处文本键笔误。
- **适配 1.4.7。** 修正值改用新名称；统治者设置改用新写法。
- **其他：** 修正几处偶发报错，例如人物死亡时连报两条错、军区治所建筑每天的报错。

## 二、军区制度重做

- **39 个史实辖区。** 军区按历史上的辖区划分，数据来自 Byzantium Overhaul: Nirvana。
- **行政与忠诚。**
  - 军区忠诚由 13 个因素决定。
  - 每个军区有五项职能、可选的施政方针，以及可以任命的属官。
- **预警、叛乱与军区工程。** 忠诚过低会先预警，再可能起兵。军区可以修建自己的工程。
- **界面：**
  - 新的军区页，可以一键设立军区、迁移治所；
  - 帝国柱石里的行政令改为统一的卡片；
  - 新增“军区辖区”地图模式。
- **军区名称**按史实和地位自动取名。
- **将军与皇位：** 将军可能称帝，军人可能政变；进京述职有风险；皇帝可以收缴兵权。
- **故事：**
  - 军区故事 34 个，地方故事 33 个；
  - 将门故事 16 个（豪族子弟出任将军、任命与世袭）；
  - 征伐时的军区出兵事件 8 个。
- **AI 拜占庭**也会使用军区和征伐系统。

## 三、帝国征伐与罗马再征服

- **九个方向的征伐：** 埃及、北非、意大利、法兰西、伊比利亚、不列颠、波斯、黑海、阿拉伯。
  - 每个方向有目标、进度和压力。
  - 德意志沿用原有的入侵与安置系统。
- **敌方会反应（17 个事件）：** 反击、求援结盟、宣布圣战、地方起义。十字军可以来自前线外隔一国的国家。
- **罗马再征服**作为征伐的总局势重新启用。
- **光复之后：** 收复罗马以后有 13 个事件和“罗马之重负”局势。

## 四、历史剧情

- **1341 年内战（两约翰之战），31 个事件。**
  - 按史料重写，从摄政之争一直写到三种结局。
  - 有花钱避免内战的路线。
- **巴尔干对手，10 个事件：** 应对杜尚的塞尔维亚和奥斯曼人渡海。
- **宫廷官职，13 个事件。**
- **帝国财政，13 个事件。**
- **故事间隔：** 军区、地方、宫廷、财政、将门、出兵六类故事共用两个月间隔，不会扎堆。

## 五、疆域与附庸

- **五种行省地位：** 内地、边镇、总督区、特许城邦、宗室封邑。地位决定长官头衔、财政制度和能用的行动。
- **内圈：**
  - 边境检查、推行罗马法；
  - 册封专制公国、迁入移民、授予普罗尼亚。
- **大区与元老院：** 设立大区并任命总凯法勒。元老院讨论四类议题，可以经它把附庸改设为行省。
- **中圈：** 同盟阶梯（朝贡 → 罗马同盟 → 行省附庸 → 设省）、10% 同盟贡金、同盟出兵。
- **外圈：** 君王大家庭的等级、帝国尊号、故省名录。
- **其他新内容：**
  - “收复故省”宣战理由；
  - 地籍清丈；
  - 附庸页；
  - 行省地位地图模式。
- **朝贡与纳币求和：**
  - 弱邻可以向帝国朝贡；
  - 帝国也可以向强邻纳币求和。
  - 纳币会引起元老院非议，非议分三级：降低贵族满意度目标，扣一次忠诚与皇权；最高一级时 AI 拜占庭不再纳币。
- **前朝王族的去处：** 设省以后，原来的王室可以入册任职。
- **边镇防务：** 劫掠、边民内迁、投诚、佣兵滋事。
- **收复与安置：** 收复的故土需要安置。

## 六、1337 年开局还原

- **以 1.4.7 原版开局为底重建。** 有意改写过的 7 个国家（拜占庭、伊庇鲁斯、塞尔维亚、保加利亚、奥斯曼、基辅、特拉布宗）和 2 个建筑型国家保留原有写法。
- **拜占庭的 1337 年 4 月 1 日：**
  - 伊庇鲁斯由安娜摄政；
  - 坎塔库泽努斯任大将军，阿波考科斯任总税务长官；
  - 约翰五世尚未加冕；
  - 艾登、萨鲁汉、卡雷西不再是盖尔米扬的附庸；拜占庭与艾登的乌穆尔结盟；
  - 与塞尔维亚、保加利亚各停战两年；
  - 加拉塔的热那亚人截走大半关税；
  - 安德罗尼卡三世重建了一支小舰队。
- **开局两年的事件：**
  - 尼科米底亚陷落、阿尔巴尼亚部落起事、伊庇鲁斯的机会、马蒂诺·扎卡里亚获释等；
  - 新行动“加冕共治皇帝”。
- **全图 15 个地区的史实校正，100 多条。** 例如：
  - 巴尔干的统治者与配偶；
  - 安纳托利亚诸侯的归属；
  - 黎凡特和伊朗的在位年代；
  - 日本南北朝；
  - 南亚新兴诸国；
  - 大元的太子。
  - 每一条的史实、原写法、改动和来源都有清单。
- **基辅：** 保留原有的立陶宛—基辅联合，作为玩法设定。
- **原版数据错误：** 思明的首都、阿尔戈斯的在位记录、辽阳的归属。
- **加拉塔之争：** 1348 年关税之争到 1352 年和约的事件链，可以借金角湾银行的钱造船；结局能削减或取消开局的加拉塔修正。
- **主线冲突：** 原版的共治皇帝链、塞尔维亚投奔事件、狄奥多拉嫁奥尔汗、皇冠宝器，不再和我们的 1341 年内战打架。

## 七、大元

- **开局：** 文宗在位日期改正；太子燕帖古思为继承人；辽阳归大元，红巾群雄因此能正常出现。
- **土司与东北部族按元代建制合并：** 大元名下的附属从 222 个减到 129 个。被并地区的文化成为首领的宽容文化。
- **内地六行省：** 河南江北、江浙、江西、湖广、陕西、四川各设一个行省，有省治衙署、长官和忠诚度。土地仍归大元，红巾起事照常。
- **1337–1351 年的朝局，12 个事件：**
  - 民变与禁令、伯颜拜大丞相、脱脱政变；
  - 白茅堤决口、贾鲁治河；
  - 帕竹取代萨迦。
- **鲁王（弘吉剌）与赵王（汪古）：** 两个蒙古宗王，作为大元附庸。

## 八、本地化

- 补了 362 条英文文本。现在所有中文文本都有英文。

## 九、性能

- 五个军区月度脉冲合并为一个，每个国家每月只判断一次。
- 故事两个月间隔：事件密度估算显示，1337–1341 年的故事数量下降约 13%。

## 十、已知问题与实验性内容

- **还没在游戏里测过的：**
  - 1341 年以后的主线冲突修复；
  - 英文界面；
  - AI 拜占庭 1339 年以后的表现。发布前用观察者模式跑到了 1339 年，期间没有发现问题。
- **错误日志里的一条原版提示：** 原版的“蒙古帝国”可成形国家会对一个无效国家求值，日志里反复出现，不影响游戏。原因还在查。
- **开局财政偏紧：** 不处理的话，拜占庭一年内会把国库用完。
- **个别故事早于史实时间出现：** 例如宫廷故事“拉丁人的书”。

## 致谢

- **制作：** 寐夜空灵、miscos330
- **军区辖区数据：** 来自“拜占庭重置:涅槃”（Byzantium Overhaul: Nirvana），已获授权。

⭐ 喜欢这个 MOD 的话，欢迎到 GitHub 仓库 https://github.com/miscos330/OEBYZ-Phoenix 点个 Star。
