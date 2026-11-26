# Wave 9B 只读审计报告：1337 法理结构、缺失首府与纹章（CoA）诊断

- **审计目标**：`Universalis Kings (EU5_1337_to_ck3)` 仓库 `repo/common/landed_titles/00_landed_titles.txt`（只读，未做任何改动）、`common/landed_titles/*.txt`、`common/coat_of_arms/coat_of_arms/*.txt` 与 `history/titles/*.txt`
- **对照基线**：CK3 `1.21.0.3 (Florin)` 原版纹章库（`CK3 1.21 vanilla coat_of_arms`）
- **审计脚本**：`audit_wave9b_dejure.py`
- **性质声明**：本报告为**只读诊断与最小改动建议**；所有涉及 `00_landed_titles.txt`（3.4 MB，上游作者维护）的变更方案均需经作者（Mare Nostrum）确认后再另立独立改动。

---

## 一、全局量化总览

### 1.1 `00_landed_titles.txt` 头衔与完整性统计

| 头衔层级 | 总数量 | 缺失 `capital` | 非法 `capital`（不存在） | 首府越界（不在自身法理子树内） | 空法理（0 下级子头衔） | 缺失 CoA（模组+原版均无） | 1337 开局有人持有且缺 CoA |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 霸权 (`h_`) | 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 帝国 (`e_`) | 69 | 0 | 0 | **9** | **27** | **15** | **1** |
| 王国 (`k_`) | 240 | 0 | 0 | **6** | **87** | **57** | **6** |
| 公国 (`d_`) | 657 | 0 | 0 | 0 | 0 | **423** | **125** |
| 伯爵领 (`c_`) | 3,819 | — | — | — | — | — | — |
| 男爵领 (`b_`) | 21,046 | — | — | — | — | — | — |

> **纹章池核对**：模组自有 CoA 定义 `1,515` 条，CK3 1.21 原版 CoA 定义 `3,977` 条，并集共 `5,475` 条；模组 CoA 别名引用失效数为 **`0`**（全部有效）。`history/titles/` 中在 1337 年有活跃持有者的头衔共 `5,776` 个。

### 1.2 其他头衔文件（除 `00_landed_titles.txt` / `zz_vanilla_titulars.txt` 外）补充统计

| 文件名 | 缺失 `capital` | 缺失 CoA（总量） | 1337 有人持有且缺 CoA |
| :--- | :---: | :---: | :---: |
| `zz_eu5_titular.txt` | 1（`k_gen_wilderness`） | 93（6 帝 / 23 王 / 64 公） | **83**（3 帝 / 22 王 / 58 公） |
| `zzz_eu5_updated_1337_titles.txt` | 1（`k_eu5_alv`） | 9（1 帝 / 7 王 / 1 公） | 1（1 公） |
| `zz_mbplus_byzantine_noble_families.txt` | 0 | 12 公 | **12** 公 |
| `07_pam_ecclesiastical_titles.txt` | 0 | 12 公 | 1 公 |
| `zzz_eu5_church_1337.txt` / `faith_heads` / `cardinalates` | 0 | 11 公 | **8** 公 |
| `zzzz_eu5_1337_religious_orders.txt` / `zz_ck2_iberian_calatrava.txt` / `mbplus_*` | 0 | 6 公 | 2 公 |

---

## 二、高优先级缺失 CoA 与首府越界清单

### 2.1 1337 开局活跃头衔中缺失 CoA（立即可见于开局地图/角色面板）

1. **帝国级（1 个）**：
   - `e_hindustan`（德里苏丹国图格鲁克王朝 `dlh_muhammad_bin_tughluq` 持有）——**1337 全图唯一一个开局持有却无 CoA 定义的帝国**，极易在地图/角色界面显示随机生成纹章。
2. **王国级（6 个）**：
   - `k_mediterranean_sea`（马略卡国王 `mll_james_iii_mallorca` 持有，实为历史马略卡王国头衔位）
   - `k_luzhen`（元朝辽阳/东北行省蒙古宗王持有）
   - `k_champa`（占婆国王 `cha_jaya_ananda` 持有）
   - `k_malayadvipa`（马来/苏门答腊君主 `jmb_akarendrawarman` 持有）
   - `k_lusung`（吕宋/汤都政权持有）
   - `k_zimbabwe`（大津巴布韦持有）
3. **公国籍（`00_landed_titles.txt` 中 125 个）**：
   - 高丽半岛全部 7 个活跃公国均缺 CoA：`d_gyeonggi`, `d_gwanseo`, `d_haeseo`, `d_gwandong`, `d_yeongnam`, `d_honam`, `d_hoseo`
   - 华北/东北/吐蕃关键公国：`d_yanbei`, `d_liaodong`, `d_songnen`, `d_changtang`, `d_lower_amur`, `d_middle_amur`
   - 东非与北非：`d_central_ethiopia`, `d_butana`, `d_southern_somalia`, `d_cyrenaica`
   - 美洲、大洋洲、中南非土著公国（如 `d_peten`, `d_mayaab`, `d_acamama`, `d_kongo`, `d_samoa`, `d_tonga` 等）
4. **外置 `zz_eu5_titular.txt` 中 83 个开局活跃头衔缺 CoA**：多为 EU5 转换的 `d_eu5_*` / `k_eu5_*` 历史诸侯与土邦头衔，以及 12 个拜占庭显贵家族公国（`zz_mbplus_byzantine_noble_families.txt`）。

> **最小无创修复建议（不改 `00_landed_titles.txt`）**：新增独立叠加文件 `common/coat_of_arms/coat_of_arms/zz_phx_1337_missing_coa_patch.txt`，优先为 `e_hindustan`、6 个活跃王国、高丽/东北/东非关键公国建立原版复用别名或历史纹章（如 `e_hindustan` 复用/定制德里新月纹章、`d_gyeonggi = k_goguryeo` 等），零风险覆盖。

### 2.2 `00_landed_titles.txt` 中首府越界（`capital` 不在自身法理子树内）

| 越界头衔 | 当前 `capital` | 首府实际归属（公国 / 王国） | 问题说明 |
| :--- | :--- | :--- | :--- |
| `e_russia` | `c_kyiv` | `d_right_bank_ukraine` / `k_ruthenia`（属 `e_west_slavia`） | 罗斯帝国首府在基辅，但基辅法理划在西斯拉夫帝国下 |
| `e_wendish_empire` | `c_south_livonia` | `d_baltic` / `k_livonia`（属 `e_west_slavia`） | 温德帝国下仅剩空的 `k_pomerania`，首府却在 `e_west_slavia` |
| `e_lingnan` | `c_guangzhou` | `d_guangdong` / `k_jiangxi`（属 `e_great_yuan`） | `e_lingnan` 下 `k_lingnan`/`k_lingxi` 全空，广州在 `e_great_yuan` 下 |
| `e_deccan` | `c_kalyana_karnakassala` | `d_karnakassala` / `k_tamilakam`（属 `e_hindustan`） | 德干帝国 5 个王国全空，南印/德干公国全部被归入 `e_hindustan` |
| `e_rajastan` | `c_central_doab` | `d_doab` / `k_delhi`（属 `e_hindustan`） | 拉贾斯坦帝国 6 个王国全空，首府指向德里多阿布 |
| `e_bengal` | `c_gaur` | `d_bengal` / `k_bengal`（属 `e_hindustan`） | 孟加拉帝国 4 个王国全空，`k_bengal` 实际在 `e_hindustan` 下 |
| `e_majapahit`（非越界但史实错位） | `c_panay` | `d_visayas` / `k_lusung`（菲律宾群岛） | 满者伯夷帝国法理首府指向菲律宾班乃岛而非爪哇 `c_trowulan` |
| `e_ilkhanate`（非越界但史实错位） | `c_basra` | `d_iraq_arabi` / `k_mesopotamia` | 伊儿汗国法理首府指向巴士拉而非大不里士 `c_tabriz` 或巴格达 `c_baghdad` |
| `k_anatolia` | `c_konya` | `d_central_anatolia` / `k_rum` | `k_anatolia` 仅含 `d_cilicia`，首府却在 `k_rum` 的科尼亚 |
| `k_caucasus` | `c_semikarakorsk` | `d_azov` / `k_pontic_steppe` | 高加索王国首府落在顿河下游亚速公国 |
| `e_eastern_europe` / `e_azania` / `e_pacific_islands` + 4 个边疆王国 | 见 JSON 报告 | 跨区首府指向 | Ck3MapGen / EU5 映射遗留，属边缘区域次要问题 |

---

## 三、1337 重大法理异常逐区剖析与最小改动建议

### 3.1 英法与不列颠群岛：`k_england` 竟位于 `e_france` 法理之下！
- **现状证据**：
  - `e_france` 下辖 `k_france`（14 公国）、`k_brittany`（1 公国）之外，还将 **`k_england`（5 公国）、`k_scotland`（3 公国）、`k_ireland`（4 公国）、`k_wales`（1 公国）** 全部纳入 `e_france`！
  - 而 `e_britannia` 虽存在于 `00_landed_titles.txt`，却是一个拥有 **0 个王国** 的空壳帝国。
  - 同时，英王爱德华三世在 1337 年持有的阿基坦（`d_guyenne`）与加斯科涅（`d_gascony`）均在 `k_france` 之下（此项本身符合 1337 封臣史实，引发百年战争法理冲突）。
- **影响**：法兰西国王只要成立 `e_france`，即自动获得对整个英格兰、苏格兰、爱尔兰与威尔士的法理宣战理由，严重失真；爱德华三世亦无法在不触碰法国帝国头衔的情况下正常构建不列颠帝国法理。
- **最小改动建议**：在 `00_landed_titles.txt`（或 1337 开局 `on_game_start` 法理重划脚本）中，将 `k_england`、`k_scotland`、`k_ireland`、`k_wales` 移回 `e_britannia`（并把 `e_britannia` 首府设为 `c_middlesex`）；`d_guyenne` 保持在 `k_france` 下以保留百年战争张力。英法合并由 Wave 9A 的 `e_phx_angevin_dual_monarchy` 决议动态完成。

### 3.2 勃艮第、神圣罗马帝国与普鲁士：`d_prussia` 归属 `k_poland`、`k_east_francia` 过度膨胀
- **现状证据**：
  - `k_poland`（属 `e_west_slavia`）直接包含 **`d_prussia`**（含 `c_upper_prussia`、`c_danzig`、`c_lower_prussia` 等 8 伯爵领），导致波兰对条顿骑士团全境天然拥有法理领主权。
  - `e_hre` 下的 `k_east_francia` 臃肿包含 **27 个公国**（横跨巴伐利亚、奥地利、萨克森、波美拉尼亚、洛林、布拉班特、荷兰、弗里斯兰），而同属 `e_hre` 的 `k_bavaria`、`k_lotharingia`、`k_frisia` 以及 `e_wendish_empire` 下的 `k_pomerania` 全部为 **0 公国空壳**。
  - 勃艮第核心被一分为二：`d_burgundy` 与 `d_flanders` 属 `k_france`，而 `d_franche_comte`、`d_savoy`、`d_provence` 属 `e_hre -> k_burgundy`。
- **最小改动建议**：
  1. 维持 `d_burgundy` 在 `k_france`、`d_franche_comte` 在 `k_burgundy`（高度契合 1337 史实：公国属法、伯国属神罗），交由 Wave 9A `k_phx_lotharingia_burgundy` 动态整合。
  2. 将 `d_pomerania` 从 `k_east_francia` 归还 `k_pomerania`（或维持神罗诸侯地位）；可将 `d_prussia` 独立或由 `k_phx_prussia` 动态脱钩，并酌情将 `d_bavaria`/`d_austria`/`d_tirol` 归还 `k_bavaria`、`d_lorraine`/`d_brabant`/`d_wallonia` 归还 `k_lotharingia`、`d_holland`/`d_friesland` 归还 `k_frisia`，以减轻 `k_east_francia` 27 公国畸形体量。

### 3.3 东欧结构性语法畸形：`e_west_slavia` 帝国下直接挂靠两个公国！
- **现状证据**：
  - `e_west_slavia` 下除 `k_poland`, `k_lithuania`, `k_white_rus`, `k_ruthenia`, `k_livonia` 之外，竟将 **`d_red_ruthenia`（9 伯爵领）与 `d_volhynia`（6 伯爵领）** 直接嵌套在 `e_west_slavia` 之下，**中间缺失王国层级**！
  - 同时 `e_west_slavia` 首府设在 `c_volodymyr`（即位于上述直属公国 `d_volhynia` 内）。
  - 与此相对，`e_russia` 仅含 `k_opolye`（9 公国）、`k_novgorod`（6 公国）、`k_permia`（5 公国）与空壳 `k_bjarmaland`，首府却指着位于 `e_west_slavia` 内的 `c_kyiv`！
  - `e_golden_horde`（金帐汗国）涵盖 5 个实辖王国（27 公国，含 `k_volga_bulgaria` 与 `k_sibir`）+ 6 个空壳王国（`k_mordvinia`, `k_cuman`, `k_kipchak`, `k_qara_dala`, `k_ob`, `k_yugra`），整体符合 1337 钦察汗国鼎盛态势，但空壳王国过多。
- **最小改动建议**：
  1. **高优先级修复**：将 `d_red_ruthenia` 与 `d_volhynia` 移入 `k_ruthenia`（或建立/启用加利西亚-沃里尼亚王国），消除“帝国直辖公国”的反常层级，防止 CK3 法理漂移与宣战逻辑异常。
  2. 将 `e_russia` 首府修正为 `c_moscow` 或 `c_vladimir`（或将 `k_ruthenia` 与 `k_white_rus` 移回 `e_russia` 并将 `e_west_slavia` 首府改为 `c_krakow`）。

### 3.4 巴尔干与安纳托利亚：`e_byzantium` 吞并全巴尔干、全安纳托利亚与高加索
- **现状证据**：
  - `e_byzantium` 下挂多达 **12 个实辖王国 + 1 个空王国**：包含 `k_serbia`、`k_bulgaria`、`k_croatia`、`k_albania`、`k_thessalonika`、`k_hellas`、`k_nikaea`、`k_rum`、`k_anatolia`、`k_trebizond`、`k_armenia`、`k_georgia`（外加空壳 `k_epirus`）。
  - 1337 年安纳托利亚的 10 个突厥贝伊国头衔（`k_ottoman`, `k_karaman`, `k_aydin`, `k_germiyan`, `k_candar`, `k_eretnid`, `k_mentese`, `k_saruhan`, `k_tekke`, `k_mediterranean_sea`）全部是 **0 公国的名义王国**；而 `k_rum`（`d_central_anatolia`, `d_cappadocia`）与 `k_nikaea`（`d_marmara`, `d_west_anatolia`）仍属于 `e_byzantium`。
- **影响**：拜占庭皇帝在 1337 年处于衰落内战边缘，却对塞尔维亚、保加利亚、克罗地亚、亚美尼亚、格鲁吉亚与整个安纳托利亚保有法理宣称；而奥斯曼或杜尚若未通过特殊决议改写法律，难以建立独立法理帝国。
- **最小改动建议**：
  1. 维持核心希腊/马其顿/色雷斯与西小亚细亚在 `e_byzantium` 下；建议将 `k_croatia` 划回 `e_carpathia`（或南斯拉夫体系），将 `k_anatolia` 首府从 `c_konya` 修正为 `d_cilicia` 内伯爵领（或将 `d_central_anatolia`/`d_cappadocia` 保留在 `k_rum` 并清理 `k_anatolia` 越界首府）。
  2. 杜尚帝国与奥斯曼帝国的法理独立重构，已由 Wave 9A `e_phx_serbian_empire` 与 `e_phx_ottoman_empire` 的动态 `set_de_jure_liege_title` 提供非侵入式玩法闭环。

### 3.5 `h_china` 与大元行省体系：23 个空壳华夏王国 + 朝/越/藏直挂 `e_great_yuan`
- **现状证据**：
  - `h_china` 下有 9 个官署帝国、1 个空壳 `e_lingnan`（下辖 2 个空王国 `k_lingnan`/`k_lingxi`），以及极度庞大的 `e_great_yuan`（**13 个实辖王国 + 23 个空壳王国**）。
  - 实辖的 13 个王国存在明显“合并失衡”：`k_hebei` 塞入 8 个公国（含山东、山西、大同、燕北、北平），`k_hunan` 塞入 6 个公国（含广西、贵州、海南），`k_henan` 包含湖北与淮东淮西，`k_jiangdong` 包含江南、浙江、福建、台湾；导致 `k_daibei`, `k_hedong`, `k_qingxu`, `k_fujian`, `k_huainan`, `k_liangzhe`, `k_lingnan`, `k_lingxi` 等 23 个传统华夏王国全部空置。
  - 此外，高丽（`k_goguryeo` 8 公国）、大越（`k_viet`）、吐蕃全境（`k_tsang` 7 公国）均直接划在 `e_great_yuan` 之下，导致 `e_goryeo` 与 `e_tibet` 沦为空壳。
- **最小改动建议**：
  1. 若作者计划在 Wave 9B 中优化中国行省颗粒度，可仅将 `d_guangdong`/`d_guangxi`/`d_haibei_hainan` 归还 `e_lingnan`（立即修复 `e_lingnan` 首府越界与空壳问题），并将 `k_tsang` 归还 `e_tibet`、`k_goguryeo` 归还 `e_goryeo`（保留 1337 实际附庸/朝贡关系于 `history/titles`，而非硬塞进元朝法理）。
  2. 其余中国行省细分改动面较大（牵动 20+ 王国历史文件），建议保持现状或分批评估，短期由 Wave 9A 的 `e_phx_ming` / `e_phx_northern_yuan` / `k_phx_great_han` / `k_phx_great_zhou` 动态接管法理。

### 3.6 印度次大陆与东南亚：`e_hindustan` 吞并德干全境、`e_majapahit` 首府错置菲律宾
- **现状证据**：
  - 印度：`e_hindustan` 囊括了 `k_delhi`(7)、`k_bengal`(7)、`k_rajputana`(4)、`k_malwa`(3) 以及巨无霸 **`k_tamilakam`（9 个公国，吞并了整个德干与南印度）**；导致同在 `00_landed_titles.txt` 中的 **`e_deccan`（5 王国）、`e_rajastan`（6 王国）、`e_bengal`（4 王国）全部为空壳**，且三者首府全部越界指向 `e_hindustan`！
  - 东南亚：`e_majapahit` 法理首府为 `c_panay`（菲律宾维萨亚斯），而非爪哇核心 `c_trowulan`；且 `k_maluku` 下挂 15 个公国，涵盖新几内亚、斐济、瓦努阿图等大片大洋洲岛屿。
- **最小改动建议**：
  1. 最小改动即可修复 `e_majapahit`：`capital = c_panay` -> `capital = c_trowulan`。
  2. 印度方面：鉴于 1337 年德里苏丹国正处于图格鲁克版图极限与德干崩解前夜，可先将 `d_karnakassala`/`d_andhra`/`d_telingana`/`d_maharashtra`/`d_konkan` 从 `k_tamilakam` 拆分回 `e_deccan`（直接修复 `e_deccan` 空壳与首府越界，同时给毗奢耶那伽罗/巴赫曼尼极佳的法理舞台）。

---

## 四、推荐分批执行路线（等待作者 Mare Nostrum 审批）

| 优先级 | 建议批次 | 触及文件 | 改动范围与收益 |
| :---: | :--- | :--- | :--- |
| **P0** | 1337 活跃头衔缺失 CoA 补丁 | 新增 `zz_phx_1337_missing_coa_patch.txt`（**不改 `00_landed_titles.txt`**） | 零风险修复 `e_hindustan`、6 个活跃王国及高丽/东北/东非关键公国缺失纹章 |
| **P1** | `00_landed_titles.txt` 最小结构修复 | `00_landed_titles.txt`（需作者批准） | ① `e_west_slavia` 下 `d_red_ruthenia`/`d_volhynia` 移入 `k_ruthenia`；② `k_england`/`k_scotland`/`k_ireland`/`k_wales` 移回 `e_britannia`；③ 修正 `e_russia`(`c_moscow`)、`e_majapahit`(`c_trowulan`)、`e_ilkhanate`(`c_tabriz`)、`k_anatolia` 首府越界/错位 |
| **P2** | 区域法理精细化（可选） | `00_landed_titles.txt`（需作者批准） | ① 拆分 `k_tamilakam` 恢复 `e_deccan`；② `e_lingnan`/`e_tibet`/`e_goryeo` 与 `e_great_yuan` 解耦；③ 梳理 `k_east_francia`（27 公国）与 `d_prussia` 归属 |
