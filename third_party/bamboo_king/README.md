# 竹子大王的社区DLC / Bamboo King's Community Flavor Pack in Phoenix (OEBYZ)

- 模组 / Mod: 竹子大王的社区DLC / Bamboo King's Community Flavor Pack（Steam 创意工坊 / Workshop 3763953914），竹子大王
- 许可 / Permission: 模型与素材经其本人同意使用（2026-11-20）：可参考、改进、借用，署名致谢。
  The maker allowed the pack's models and materials to be referenced, improved and borrowed, with credit (2026-11-20).
- 本文件夹 / This folder: this README and one manifest per use. Each manifest is written by its generator in the
  tools repository and lists every copied file with its path in the pack, its path here, its size and its SHA-256.

## 三处用途 / The three uses

| 用途 / Use | 本模组位置 / Where in this mod | 前缀 / Prefix | 清单 / Manifest | 生成器 / Generator |
|---|---|---|---|---|
| 大元肖像官服与冠帽：四档圆领袍、蒙古交领衣、蒙古帽、展脚幞头、垂翅幞头（大元皇帝、诸王、朝臣、行省长官）/ Yuan portrait robes and hats | `in_game/gfx/models/portraits/attachments/oe_yuan_portraits/`, `main_menu/gfx/portraits/` | `oe_yp_` | `MANIFEST.md` | `gen_yuan_portraits.py` |
| 东罗马军队的单位模型：罗马盔、具装覆面盔、希腊短袖甲、罗马束腰甲与札甲、斯帕塔剑、鸢盾、扇形盾、拉布兰旗（只给 BYZ，传统与文艺复兴时代）/ Byzantine unit models (BYZ only, ages 1-2) | `in_game/gfx/models/units/oe_byz_units/`, `main_menu/gfx/unit_graphics/*/oe_bu_byz_units.txt` | `oe_bu_` | `MANIFEST_byz_units.md` | `gen_byz_units_look.py` |
| 大元军队的单位模型：护脸盔、札甲、范阳笠、绑腿、直刀与雁翎刀、虎头盾、半具装马铠（大元、内地与边地行省、宗王、北元，传统与文艺复兴时代）/ Yuan unit models (CHI, its branch secretariats and princes, YUA; ages 1-2) | `in_game/gfx/models/units/oe_yuan_units/`, `main_menu/gfx/unit_graphics/*/oe_yu_yuan_units.txt` | `oe_yu_` | `MANIFEST_yuan_units.md` | `gen_yuan_units_look.py` |

Meshes and textures are byte-identical copies under new names; the `.asset` files, accessories, genes, portrait
modifiers, triggers, texture variations and attachment lists are written by Phoenix (adapted, not copied). No file
replaces a vanilla file or a file of the pack.

## 没有拿的 / Not taken

- The pack's `acg_` set (flag bearer, donkey auxiliary and their attachment lists): it comes from another mod and is
  not covered by the maker's permission.
- Every file that keeps a vanilla or DLC name (`unit_`, `male_` meshes and the like) and the seven files that replace
  whole vanilla files (languages, hair, headwear, attachment lists), the pack's unit-type overrides and its redefinition
  of vanilla material groups.

## 贴图 / Textures

The `.dds` textures are kept out of git like the mod's other art (`.gitignore`); each generator copies them from the
pack after checking their hashes, and the release script packs the ignored `.dds` files of the working tree.

## 致谢 / Credit

竹子大王的社区DLC / Bamboo King's Community Flavor Pack（3763953914），竹子大王，经其本人同意使用。
