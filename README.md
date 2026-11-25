# Project Phoenix (《凤凰计划》 / OEBYZ) v30.2 — Europa Universalis V 1.4.9

**Target Game Version:** Europa Universalis V `1.4.*` (`1.4.9`)  
**Languages:** Complete Simplified Chinese & English (`l_simp_chinese` + `l_english`, 100% key parity across 77,855+ main-mod keys)  
**Repository:** https://github.com/miscos330/OEBYZ-Phoenix

> **Save Compatibility & Submod Matrix Notice / 存档兼容性与子模组矩阵说明**  
> **EN:** `v30.2` is **not** compatible with saves from earlier versions — always start a new campaign. **All-Eras Historical Bookmarks** (`3844848618`) and **The Fallen Eagle (361–768 AD)** are **standalone-capable**. **1453 Fourth Rome** (`3845210560`) uses a **dual dependency** architecture and requires **BOTH** *Project Phoenix* (`3667460405`) and *All-Eras Historical Bookmarks* (`3844848618`) enabled above it. When using **Glorp UI 1.4.9 & Phoenix UI Overhaul**, always place it **at the very bottom** of your playset.  
> **中文：** `v30.2` **不兼容**旧版本存档，请新开一局。**《全时代历史剧本拓展包》**（`3844848618`）与**《雄鹰陨落：古典晚期 361–768》**支持**完全独立运行**；**《1453 第四罗马》**（`3845210560`）采用**双重依赖**架构，游玩时须按顺序同时启用《凤凰计划》主模组（`3667460405`）与《全时代》（`3844848618`）；若启用**《Glorp UI 1.4.9 凤凰适配增强》**，请务必排在播放集**最底部**。

---

## Overview / 模组定位与 v30.0–v30.2 里程碑

### English
- **Full Roman 79-Theme Empire & 500-Year Institutional Overhaul (1337–1836):** Rebuilds the Eastern Roman Empire from the 1337 crisis through Imperial Authority, **4 Praetorian Prefectures × 12 Classical Dioceses** + 10 Eastern Exarchates spanning **3,182 Roman tiles** (hub-only food-safe posts, Prefecture-capped Senate voting with O(1) preview, 79-theme map mode, and seamless `BYZ → ROM` survival), Pragmatica Sanctio & Imperial Chancery deepening, multi-tier subject ladder, and late-game Empire Entropy through modern constitutional endgames.
- **3D Landmarks, Greek Dynamic Toponymy, Roman Roads & Monasteries (`v30.1–v30.2`):**
  - Custom 3D **Hagia Sophia** (`standard_building` map-object shader) & Varangian/Byzantine **Skoutarion** shield;
  - **19,539 Greek dynamic place names**, **155 Roman imperial road segments**, **12 Balkan monasteries**, and **16 Anatolian monastery restoration decisions**;
  - **100% Native R29 DDS Icons**, built-in **Historical Encyclopedia** (`oe_wp26_encyclopedia`), and **Classical Music Player / Jukebox**.
- **Pan-Eurasian Core Overhauls (`v26.0–v30.2`):**
  - **Unified Culture & Religion Engine:** Safe-floor O(1) assimilation gradient, unblocked Roman subject conversion & provincialization, renewable 30-year Romanization waves, Pentarchy border guards, and **19 Game Rules**.
  - **Teutonic Order & Great Yuan Reworks:** Grounded 3-tier Ordensland + autonomous Livonia (`LIV`) + 4 bounded Ordensmarks (127 tiles), 1385 Krewo & 1440 Prussian Confederation crises, 1525 Secular Prussia vs Ordensstaat; Great Yuan cuts location overhead by 98%+, calibrates 1337 Zhongshu opening finances, reworks Red Turban pacing, and adds Four-Class & 1342 Marignolli flavor.
  - **East Asia & Ming Celestial (*Pax Solis*, permitted):** EU5-native Reign Titles, O(1) Three-Stage Mandate Cycle, Bilateral Royal Favor Tributary System, Five Court Policies, 17 Ming events, 15 East Asian landmarks, and 72 clean-room DDS assets.
  - **Interactive Situations & High-Contrast UI:** 32 custom active situations with native `?` play guides, 13px+ dark-paper UI contrast across all panels (including widened Celestial Secretariat resolution headers), and pre-1337 closed-interval date guards.

### 中文
- **全罗马 79 军区与五百年制度重制（1337–1836）：** 以东罗马帝国为核心，自 1337 危局起步，涵盖帝国权威、覆盖全罗马 **3,182 格**的 **四大近卫大区 × 十二古典管区** + 十大东方大军区（枢纽防饥荒治所、大区封顶元老院与 O(1) 票型预览、79 军区专属地图模式与 `BYZ → ROM` 无缝换标存续）、《御敕法典》与帝国枢密深化、多阶附庸设省体系及帝国熵增直至近代宪政终局。
- **3D 奇观、希腊动态地名、罗马大道与修道院（`v30.1–v30.2`）：**
  - 实装 3D **圣索菲亚大教堂**（`standard_building` 地图物件着色器）与东罗马/瓦兰吉 **Skoutarion 鸢形盾**；
  - 新增 **19,539 条希腊语动态地名**、**155 段罗马帝国大道网络**、**12 座巴尔干历史修道院**与 **16 项安纳托利亚修道院兴复决议**；
  - 补全 **100% 原生 R29 DDS 图标**，内置**凤凰历史百科**与**古典点唱机**。
- **欧亚核心系统大修（`v26.0–v30.2`）：**
  - **文化宗教统一引擎与 19 项开局规则：** 安全下限 O(1) 同化梯度、打通罗马附庸改宗设省闭环、可续期 30 年罗马化浪潮、五牧首边界守卫与《同化与传教节奏》规则。
  - **条顿骑士团与大元重塑：** 条顿直辖核心领 + 自治利沃尼亚（`LIV`）+ 4 块东疆统领边区（127 格），涵盖克雷沃联合、普鲁士邦联与 1525 双终局；大元地区运算削减 98%+，校准 1337 中书省开局财政，重构红巾军稳定曲线并新增四等人制与马黎诺里风味。
  - **东亚与大明天命（《萬方景明》授权）：** EU5 原生年号、O(1) 三阶段王朝天命周期、双向皇恩朝贡、五项朝堂国策、17 项大明历史事件、15 座东亚奇观与 72 枚洁净室 DDS 资产。
  - **全互动局势与高对比界面：** 32 项活跃自定义局势全覆盖原生 `?` 指引，全界面 13px+ 高对比深色底板（含天朝秘书处宽幅决议标题），内置前 1337 双边日期守卫。

---

## Official Optional Submod Matrix & Load Order / 官方子模组矩阵与推荐加载顺序

Place enabled submods **below (after)** the Project Phoenix main mod in the order shown below:

| # | Package / 子模组 | Role & Dependency / 定位与依赖 | Workshop / Version |
|---:|---|---|---|
| 1 | **Project Phoenix (OEBYZ)** (`oebyz.phoenix.main`) | Main overhaul (1337–1836). Bundles *Descriptions Expanded* (`third_party/descriptions_expanded/`) — do not subscribe separately. | [`3667460405`](https://steamcommunity.com/sharedfiles/filedetails/?id=3667460405) · `v30.2` |
| 2 | **All-Eras Historical Bookmarks** (`oebyz.phoenix.all_eras`) | **5 Eras (`1204 / 1337 / 1453 / 1648 / 1776`)**, CK3 5+1 theater rail, **127/127 bespoke oil portraits** (incl. 25/25 1204 rulers), 157 3D character DNAs (102 genes/char), dynamic 1204 Nicaea name & lore, 6 viceroyalties, 1453 BYZ core. **Standalone-capable.** | [`3844848618`](https://steamcommunity.com/sharedfiles/filedetails/?id=3844848618) · `v30.2` |
| 3 | **1453 Siege of Constantinople & Fourth Rome** (`oebyz.phoenix.1453_fourth_rome`) | Nova Elysia exile campaign with systemic `ELR` isolation, 8 imperial edicts, Restored Empire IO, **5 custom 3D Elysian Great Wonders**, Elysian Guard 3D units & Greek New World names. **Dual dependency: requires #1 + #2 above it.** | [`3845210560`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845210560) · `v30.2` |
| 4 | **National Destinies — Deep Integration** (`oebyz.phoenix.national_destinies`) | Authorized deep integration of *National Destinies* (`3668193813`) + Chinese loc (`3744757513`), synchronized with Phoenix formables via `on_new_country_formed` + yearly pulse (50,702 EN/ZH keys). *(Or use lightweight **ND Compat Bridge** `oebyz.phoenix.compat.national_destinies` with external Workshop `3668193813`.)* | Optional · `v30.2` |
| 5 | **Map Beautification — Pick 1 of 3 Styles** | Choose **one**: Classic Atlas (`oebyz.phoenix.map_beauty`), High-Contrast Political (`oebyz.phoenix.map_beauty_hc`), or Imperial Parchment (`oebyz.phoenix.map_beauty_parchment`). Zero-shader + 2 live additive map modes. | Optional · `v30.2` |
| 6 | **Glorp UI 1.4.9 & Phoenix UI Overhaul** (`oebyz.phoenix.glorp_ui`) | Authorized UI overhaul harmonized with Phoenix panels, Celestial Secretariat resolutions, and observer-safe season controls. **Always load last (bottom of playset).** | Optional · `v30.2` |
| ★ | **The Fallen Eagle (361–768 AD)** (`oebyz.phoenix.fallen_eagle`) | **Standalone Late Antiquity Overhaul** (run alone, do not mix with #1/#2/#3): **6 Eras (`361/395/476/532/632/768`)** with 6-Era CK3 Atlas UI, 8 flagship 532 oil portraits + 30 gilded heraldic medallions, 176 3D DNAs, 28 mipmapped COA emblems, 4 Late Antiquity ages, 12 institutions & 6 custom 3D monuments. | Standalone · `v30.2` |

- **Bundled Overlay Note:** If you also load *Descriptions for Every Tile* or *Every Historical Character*, place them **above (before)** Project Phoenix.
- **Manual Install:** Download archives from [GitHub Releases](https://github.com/miscos330/OEBYZ-Phoenix/releases), extract into `Documents\Paradox Interactive\Europa Universalis V\mod\`, and enable in the order above.

---

## Compatibility / 兼容性

- Built strictly for **Europa Universalis V `1.4.*` (`1.4.9`)**; not save-compatible with older versions.
- Rewrites portions of the 1337 start setup, a minimal set of vanilla event/GUI files, and 3 Red Turban situation files; avoid stacking with other Byzantine or 1337 total overhauls.

---

## Credits & Licence / 致谢与许可

- **Project Repository / 项目仓库：** [OEBYZ-Phoenix](https://github.com/miscos330/OEBYZ-Phoenix)
- **Theme-Region Data / 军区辖区数据：** *Byzantium Overhaul: Nirvana* ([Workshop 3602306286](https://steamcommunity.com/sharedfiles/filedetails/?id=3602306286)), used with permission.
- **Historical Descriptions / 历史介绍文字：** *Descriptions Expanded* ([Workshop 3838927963](https://steamcommunity.com/sharedfiles/filedetails/?id=3838927963)), used under **CC BY-SA 4.0**. Project Phoenix's additional entries are likewise offered under **CC BY-SA 4.0**; complete upstream licence and attribution records are preserved in `third_party/descriptions_expanded/`.
- **East Asia & Ming Celestial / 《萬方景明》授权协作：** EU4 *Pax Solis* / 《萬方景明》 ([Workshop 2334831204](https://steamcommunity.com/sharedfiles/filedetails/?id=2334831204)), used with formal permission (`third_party/wanfang_jingming/`).
- **Late-Antique Art, Heraldry & DNA / *The Fallen Eagle* 授权协作：** CK3 *The Fallen Eagle* ([Workshop 2243307127](https://steamcommunity.com/sharedfiles/filedetails/?id=2243307127)), used with formal permission (`third_party/the_fallen_eagle/`).
- **National Destinies & Glorp UI / 深度整合授权：** *National Destinies* ([Workshop 3668193813](https://steamcommunity.com/sharedfiles/filedetails/?id=3668193813)) & Chinese Localization ([Workshop 3744757513](https://steamcommunity.com/sharedfiles/filedetails/?id=3744757513)), and *Glorp UI* ([Workshop 3601047146](https://steamcommunity.com/sharedfiles/filedetails/?id=3601047146)), integrated with formal permission (licence notices preserved in each submod's `third_party/`).
- **Special Thanks / 特别致谢：** Bamboo King's Community Flavor Pack ([Workshop 3763953914](https://steamcommunity.com/sharedfiles/filedetails/?id=3763953914), `third_party/bamboo_king/`), plus authorized 3D/historical reference collaborations (*Third Odyssey*, *Praecepta Militaria*, *ERGP*, *Orbis Romanus*, *Basileia Romaion: 1337*, *The Reich*, *Rise of the British Empire*, *Refined Colonization*, *Manchu-Qing Flavour Expansion*, *Flavorium Universalis - Rhomania*, *MEIOU and Taxes*, and *Celestial Empire Expansion*).
