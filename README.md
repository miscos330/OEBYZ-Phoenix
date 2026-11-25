# Project Phoenix (《凤凰计划》 / OEBYZ) v40.0 — Europa Universalis V 1.4.9

**Target Game Version:** Europa Universalis V `1.4.*` (`1.4.9`)  
**Languages:** Complete Simplified Chinese & English (`l_simp_chinese` + `l_english`, 100% key parity across 87,700+ main-mod keys)  
**Repository:** https://github.com/miscos330/OEBYZ-Phoenix  
**制作 / Made by:** 寐夜空灵、miscos330 (`Made by: 寐夜空灵, miscos330`)

> **Save Compatibility & Streamlined 10-Package Pure Matrix Notice / 存档兼容性与 10 包纯净矩阵说明**  
> **EN:** `v40.0` is our **Interactive Mechanics, Era-Aware AI Overhaul & Live-Acceptance Closure Release** verified against **54/54 EU5 1.4.9 CI rules (`R01–R54`)**; it is **not** compatible with saves from earlier versions — always start a new campaign. **Fourth Rome (Third Odyssey P3: `ELR` Exodus, 5 3D Elysian Wonders & 10 Systems)** is **cleanly integrated directly into All-Eras Historical Bookmarks (`1444.11.11` Day After Varna)** — keeping the official matrix streamlined at **10 packages**! Both **All-Eras Historical Bookmarks (`1204/1337/1444/1648/1776/1821`)** (`3844848618`) and **The Fallen Eagle (`361–768 AD`)** (`3845632550`) are **100% standalone-capable** with zero main-mod dependency. When using **Glorp UI 1.4.9 & Phoenix UI Overhaul** (`3845632981`), always place it **at the very bottom** of your playset.  
> **中文：** `v40.0` 为**不开新剧本、全量补全交互局势、时代感知 AI 重构与实机验收闭环版本**（通过 **54/54 条 EU5 1.4.9 静态门禁 `R01–R54`**），**不兼容**旧版本存档，请新开一局。**《第四罗马（三奥德赛 P3：5 座 3D 奇观与 10 套系统）》原生并入《全时代历史剧本》的 `1444.11.11` 瓦尔纳次日剧本**（开局提供“坚守君堡反攻 / 西迁第四罗马”双路线选择，并支持 AI 完整自动西迁），官方矩阵保持 **10 包**。**《全时代历史剧本》**（`3844848618`）与**《雄鹰陨落 361–768》**（`3845632550`）均支持**100% 独立运行**；**《Glorp UI 1.4.9 凤凰适配增强》**（`3845632981`）请始终排在播放集**最底部**。

---

## Overview / 模组定位与 v40.0 玩法深化、AI 重构与实机闭环亮点

### English
- **v40.0 Interactive Mechanics, Era-Aware AI & Live-Test Closure (`54/54 R01–R54` CI):**
  - **10 New Interactive Era Situations (20 Total across Extended Eras) + 15 Cultural Fusion Decisions + 14 Iconic Wonders:** Expanded All-Eras (`WP45`) and Fallen Eagle (`WP46`) from 5 -> **10 interactive Situations each** (every extended era now has `>= 2` simultaneous interactive Situations with `30` actions, custom GUI panels, and multi-branch culmination events), added **15 Dynamic Cultural Fusion pathways** + **14 Historical World Wonders** (`Taq Kasra`, `San Vitale`, `Daming Palace`, `Aachen Chapel`, `House of Wisdom`, `Versailles Hall of Mirrors`, `Red Fort`, `Winter Palace`, `Porcelain Tower of Nanjing`, `Registan`, `Independence Hall`, etc.).
  - **5-Tab Phoenix Master Console & 6 Great Power Systems (`WP33` + `WP35`):** Upgraded the zero-override Command Dock to **5 tabs (`26` live SGUI buttons)** adding Tab 5 *World Compass* (`oe_wp33.201–.206`), deepened Ottoman/Persian/Russian/Indian mechanics to full 3-stage arcs, added dedicated **France (`FRA`)** & **Spain (`CAS`/`SPA`)** Great-Power systems, and purged all internal work-package labels (`WP47`/`WP33` -> `0`).
  - **Era-Aware AI Logic & Strategic Ecology Overhaul:** Fixed cross-era AI personality collisions (no longer turning 1653 Qing or 1655 Edo Japan into European Concert arbiters), added **Tokugawa Sakoku Guardian** (`1635–1853`), stripped vanilla `explore_african_coast` leaks from New World colonies / East Asia / pre-1415 powers, replaced Qing's Ming Zheng He corridor with the **Qing Inner Asia Corridor**, added **1644–1685 Ming–Qing Existential Total War** renewal (`oe_wp45_1648.26`) + 1204/1776/1821 total-war fervor, locked Late Antiquity (`< 1000`) cross-continent wars, and disabled unsolicited AI peacetime truce spam.
  - **+424 Historical Adult Retinues & 10 New Museum-Grade Bookmark Oil Paintings:** Added `+304` verified historical adult ministers/commanders across `1204–1821` and `+120` across `361–768` (`0` duplicates, `0` underage), and integrated 10 bespoke era paintings (`1204` Onon Kurultai & Château Gaillard, `1776` Golden Horn / Winter Palace / Chengde, `1821` Agia Lavra / Field of Mars / Lahore Durbar / Canton Thirteen Factories / Carabobo) natively into All-Eras 32/32 theater cards.
  - **Full Live-Test Error Closure:** Added 45 era- & culture-aware country descriptions (`U1`), fixed Qing `MCH->CHI` Celestial track (`U2`), added `dadu -> Beijing` (`1421+`) & `00_` Joseon name priority (`U4`), suppressed old 1453 Day-1 popups in 1444 (`S1`), enabled Fourth Rome AI Exodus auto-progression (`R4`), sanitized all era setup templates against vanilla law/policy/advance gates (`R1`/`R2`), cleared `2,222 -> 0` Fallen Eagle undiscovered dormant capitals (`R3`), clamped 7 building efficiency ratios `<= 0.0120` (`N7`), fixed Glorp UI `cmf_change_variable_map` & National Destinies Murmur3-32 hash collision (`R7`).
- **v36.0–v39.0 Core Pillars (Preserved & Polished):**
  - **1444.11.11 Varna Aftermath + Built-In Fourth Rome**, **Full Roman 79-Theme Empire & Byzantine Core (`WP32`)**, **30 Dynamic Colonial Ensigns across 14 Civilization Families + Zero-Doubling Naming**, **British 53-Task Empire Tree & Multi-Tier Subject Actions**, **15 Canonical Zero-Collision `O_*` Tags**, **30-State 1815 German Confederation**, and **3D Hagia Sophia + 19,539 Greek Place Names**.

### 中文
- **`v40.0` 交互局势扩充、全时代 AI 重构与实机验收全面闭环（`54/54 R01–R54` 门禁全过）：**
  - **新增 10 套交互式时代局势 + 15 条文化融合路径 + 14 座历史奇观：** 全时代（`WP45`）与雄鹰陨落（`WP46`）各自从 5 套扩充至 **10 套交互局势**（全 11 个扩展时代均拥有 `>= 2` 套同步局势、30 项专属互动、独立局势 GUI 与多分支终局事件），同步新增 **15 条跨文明文化融合决议** 与 **14 座历史奇观建筑**（泰西封大拱、圣维塔莱、大明宫、栖霞寺、亚琛宫廷礼拜堂、智慧宫、临安太学、大报恩寺琉璃塔、雷吉斯坦、凡尔赛镜厅、德里红堡、冬宫、独立厅、雅典议会等）。
  - **凤凰总控台 5 分页升级 + 六大强权三阶段机制（`WP33` + `WP35`）：** 零覆盖悬浮指令台升级为 **5 分页（26 个实时 SGUI 按钮）** 新增「寰宇指引」面板，彻底清零玩家界面内的 `WP47/WP33` 内部代号；奥斯曼/波斯/罗斯/印度全部拓展为 3 阶段完整弧线，并新增**法兰西**与**西班牙**专属强权系统。
  - **全时代 AI 逻辑与战略生态重构：** 修复三套 AI 性格系统互相踩踏问题（1653 清与 1655 幕府不再被强盖「欧亚均势调停者」），新增 **`1635–1853` 锁国幕藩保守派**性格，零覆盖清理美洲殖民地/东亚/1415 前国家被原版污染的「探索非洲海岸」，将清朝走廊由郑和南洋改为**大清龙兴与蒙疆藏战略走廊**，加入 **`1644–1685` 明清不死不休复战引擎**（及 1204/1776/1821 存亡死战激励）、`361–768` 古典跨洲参战锁，并关闭 AI 乱签 5 年边境停战互动。
  - **`+424` 名成年历史群像与 10 张新增时代战区油画：** `1204–1821` 新增 `+304` 名、`361–768` 新增 `+120` 名史实成年名臣名将；全时代原生合入 10 张按年代新绘古典油画（1204 斡难河忽里台/盖拉尔城堡、1776 金角湾/冬宫/承德、1821 圣拉夫拉/马尔斯校场/拉合尔/广州十三行/卡拉沃博），32 张全齐零重复。
  - **实机测试问题全量闭环：** 补齐 45 条按时代与文化区分的国家介绍（`U1`）、修正清朝 `MCH->CHI` 串轨大元释放北庭乌鲁斯与征东元帅府（`U2`）、1421 后大都改名北京与朝鲜优先命名（`U4`）、关闭 1444 首日误弹的旧 1453 围城事件（`S1`）、打通第四罗马 AI 自动西迁航程（`R4`）、全面清洗 11 剧本模板缺科技/不合法法律政策（`R1`/`R2`）、清零雄鹰陨落 `2,222` 处未探索休眠首都（`R3`）、压平 7 类建筑人力/水手效率（`N7`）、修复 Glorp 8 处 CMF 报错与国家命运 Murmur3 哈希碰撞（`R7`）。
- **既有核心体系（`v26.0–v39.0` 完整保留并深化）：**
  - `1444.11.11` 瓦尔纳次日与内置第四罗马、全罗马 79 军区与拜占庭深度机构（`WP32`）、30 面 14 族殖民纹章旗与去叠词命名、英国 53 任务帝国树与多阶附庸外交、3D 圣索菲亚与 19,539 条希腊动态地名、《萬方景明》东亚天命体系与防弹窗冷却叙事节奏。

---

## Official Optional Submod Matrix & Load Order / 官方 10 包纯净矩阵与推荐排序

Place enabled submods **below (after)** the Project Phoenix main mod in the order shown below:

| # | Package / 子模组 | Role & Dependency / 定位与依赖 | Workshop / Version |
|---:|---|---|---|
| 1 | **Project Phoenix (OEBYZ)** (`oebyz.phoenix.main`) | Main overhaul (`1337–1836`, WP32 / WP33+WP47 5-tab UI dock / WP35 6 Great-Power Systems / Era-Aware AI Overhaul / 45 Era Country Descs, 87,700+ EN/ZH keys, `54/54` CI pass). Bundles *Descriptions Expanded*. | [`3667460405`](https://steamcommunity.com/sharedfiles/filedetails/?id=3667460405) · `v40.0` |
| 2 | **All-Eras Historical Bookmarks (+ Built-In Fourth Rome)** (`oebyz.phoenix.all_eras`) | **6 Eras (`1204/1337/1444/1648/1776/1821`)** + **Integrated Standalone Fourth Rome (`1444` Dual-Path + AI Exodus, 5 3D Wonders & 10 Systems)** + **32 Museum-Grade Era Banners** + 10 interactive situations, 17 era decisions, 24 wonders & +304 retinues (`54/54` CI). **100% Standalone-capable.** | [`3844848618`](https://steamcommunity.com/sharedfiles/filedetails/?id=3844848618) · `v40.0` |
| 3 | **National Destinies — Deep Integration** (`oebyz.phoenix.national_destinies`) | Authorized integration of *National Destinies* (`3668193813` + ZH `3744757513`), 50,702 EN/ZH keys, 0 hash collisions (`54/54` CI). *(Or use lightweight **ND Compat Bridge** [`3845632818`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632818) with external Workshop `3668193813`.)* | [`3845632867`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632867) / [`3845632818`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632818) · `v40.0` |
| 4 | **Map Beautification — Pick 1 of 3 Styles** | Classic Atlas ([`3845632643`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632643)) / High-Contrast ([`3845632683`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632683)) / Imperial Parchment ([`3845632746`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632746)). Zero-shader + 2 live map modes. | [`3845632643`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632643) / [`3845632683`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632683) / [`3845632746`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632746) · `v40.0` |
| 5 | **Glorp UI 1.4.9 & Phoenix UI Overhaul** (`oebyz.phoenix.glorp_ui`) | Authorized UI overhaul harmonized with WP33 5-tab Phoenix dock, 0 CMF errors, zero ZH button clipping & `54/54` CI. **Always load last.** | [`3845632981`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632981) · `v40.0` |
| ★ | **The Fallen Eagle (361–768 AD)** (`oebyz.phoenix.fallen_eagle`) | **Standalone Late Antiquity Overhaul** (run alone — do not mix with #1/#2): 16 Late Antique cultures, pre-1054 Christianity & Arianism, **24 parchment maps + 24 era banners**, 10 interactive situations & GUIs, 16 decisions, 18 wonders, +120 retinues & 0 undiscovered capitals (`54/54` CI pass). | [`3845632550`](https://steamcommunity.com/sharedfiles/filedetails/?id=3845632550) · Standalone · `v40.0` |

- **Bundled Overlay Note:** Do not subscribe separately to *Descriptions Expanded*. Place *Descriptions for Every Tile* or *Every Historical Character* **above (before)** Project Phoenix if used.
- **Manual Install:** Download archives from [GitHub Releases](https://github.com/miscos330/OEBYZ-Phoenix/releases), extract into `Documents\Paradox Interactive\Europa Universalis V\mod\`, and enable in the order above.

---

## Credits & Licence / 制作与致谢

- **制作 / Made by:** 寐夜空灵、miscos330 (`Made by: 寐夜空灵, miscos330`)
- **Project Repository / 项目仓库：** [OEBYZ-Phoenix](https://github.com/miscos330/OEBYZ-Phoenix)
- **Licensed Integrations / 授权整合** *(Complete provenance & licences preserved in `third_party/`)*:
  - *Byzantium Overhaul: Nirvana* (`3602306286`), *Descriptions Expanded* (`3838927963`, CC BY-SA 4.0, see `third_party/descriptions_expanded/`), EU4 *Pax Solis / 萬方景明* (`2334831204`, see `third_party/wanfang_jingming/`), CK3 *The Fallen Eagle* (`2243307127`, see `third_party/the_fallen_eagle/`), *Bamboo King's Community Flavor Pack* (`3763953914`, see `third_party/bamboo_king/`), *National Destinies* (`3668193813`) & Chinese Localization (`3744757513`), and *Glorp UI* (`3601047146`).
- **Reference & Inspirations / 参考与致谢** *(Historical & mechanical design research, cleanly implemented natively for EU5 1.4.9; see `third_party/wp32_provenance/` & `third_party/wp35_provenance/` for asset audit notes)*:
  - *Third Odyssey* (`387726157`), *Praecepta Militaria* (`3814299725`), *The Reich* (`3823496063`), *Rise of the British Empire* (`3621489583`), *Rhomania: Journey to the West* (`3813494789`), *Ananeosis Autokratorias* (`3604070407`), *Terra et Mare* (`3749893974`), *Basileia Romaion 1337* (`3618199037`), *Hellenic Renaissance* (`3786940706`), *Eastern Roman Great Projects* (`3655093103`), *Leo VI's Mass Vassal Directives* (`3766246044`), *Orbis Romanus* (`3776054764`), *Byzantine Resurgence* (`1088606279`), *Subjects Expanded* (`1834079712`), *Governments Expanded* (`1596815683`), *Flavour and Events Expanded* (`2185445645`), *Great Ming 200 Provinces* (`2187691560`), *RICE* (`2273832430`), *Medieval Arts* (`2452585382`), *Cities of Wonder 3* (`2901477267`), *Extended Timeline* (`217416366`), *Refined Colonization*, *Flavorium Universalis*, *MEIOU and Taxes*, and *Celestial Empire Expansion*.
