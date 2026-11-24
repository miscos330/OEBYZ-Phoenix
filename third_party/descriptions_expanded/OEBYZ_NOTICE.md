# Descriptions Expanded in Phoenix (OEBYZ)

This folder holds the licence, credits and source list of **Descriptions Expanded: Countries, Cultures, Dynasties & More**
(Steam Workshop 3838927963), version 1.2.3 (see `CREDITS.md` and `LICENSE` for upstream attribution). Phoenix includes
that mod's description texts and adds its own.

## What is included unchanged

Byte-identical copies of version 1.2.3 (SHA-256):

- `in_game/common/customizable_localization/lde_history_entries.txt` `8078b8b16c82e9101305446490aca7a6ff6d838709ba37a750c59f0f4e45486f`
- `in_game/localization/simp_chinese/lde_history_entries_l_simp_chinese.yml` `ef6b9f980ac86953bb84a3a9c597b2e4aacd2438b930bddb134130283672ee5b`
- `in_game/localization/simp_chinese/replace/lde_history_entries_replace_l_simp_chinese.yml` `ee2c2fbce3d7c5b13a0b3b80550e8588a998ea15fd4ccfda70147e6db1a33ea2`
- `in_game/localization/english/replace/lde_history_entries_replace_l_english.yml` `bef0c846b82f1928a9c824ee96fd293dd595daec55cfb1c8ec97ef8dbebb2c03`
- `LICENSE` `98d215b1d5affaf6e75e6e1d7b2df3b945b5dfd3479ad700d5c2807dd08609ea`
- `LICENSES/CC-BY-SA-4.0.txt` `091d08965bb70d444daccb62c5bcc4345cd4d6a65267da1f06564c95d25d9abb`
- `LICENSES/MIT.txt` `7789db1e9db4f7dedd32ba79638aa49f6fa1dc4d15fda491cf89923826781343`
- `CREDITS.md` `63fd891abd9da18c103544c6af03a904eddc79bcc91e5551d4392db0df5ecbff`
- `README.md` `a1339cc22b76659c19ad6014613d3c31dd0b25dde72f5d14fd5e9d9c8fc2cff2`
- `README.zh-CN.md` `2e8d1568621bc1ca19637e8795b26a5fe6e58b39fbae52d0fcbc273dae3d1eb2`
- `sources/sources.jsonl` `4dd0c954ab020a8be0f371d459a134ee7b9ad3705601baa9c715382a3466bffe`

## What Phoenix changed or added

- `in_game/localization/english/lde_history_entries_l_english.yml` (upstream SHA-256 `71f7df07dfeb0baede6419852cf1271b47d557dc4c4400f04b290d7d077e4d4b`):
  removed one stray CJK string in `lde_dyn_takou_dynasty` so the English localization file contains zero CJK characters;
  all other lines are unchanged from version 1.2.3.
- `in_game/gui/zz_lde_history_tooltips.gui`: the country, culture and dynasty tooltips first show Phoenix's own text
  for the object when there is one, otherwise the Descriptions Expanded text as before. Nothing else in the file is changed.
- `in_game/common/customizable_localization/oe_lde_overlay.txt` and `main_menu/localization/*/oe_lde_overlay_l_*.yml`:
  54 new descriptions for countries, dynasties and cultures not covered by Descriptions Expanded, and 8 adapted ones:
  for CRI, QAS, HCN, OTC, BGT, OGE, LNG, SYG the first paragraph is rewritten for Phoenix's setup (the Yuan princes are named
  by their titles; Crimea begins as the 1337 Crimean Tumen) and the later paragraphs of the Descriptions Expanded entry follow unchanged.
  For WAL, EPI, FEO, GAZ, SAO, ACH, NEO, ATH, gabras_dynasty, pontic_greek_culture, GLH, SMS, nakh_culture, ryazanian, CYP, GEO, HLG, QAR, AQQ, CDL, LNG, duan_dynasty, SRB, MOS, RUS, IRA, ETH, MAM, BYZ the Descriptions Expanded entry is shown with single sentences replaced where it
  contradicts Phoenix's 1337 start, states as settled what the sources leave open, or omits key v7.0-v7.2 figures. For AAI, AQQ, CYP, EPI, ERE, FEO, GRG, HCI, IME, INJ, JAL, KRT, MZF, NAX, SME, SRB, SUT, TLM, hazara_culture, iraqi_culture, laz_culture, arghunid_dynasty, bagrationi_dynasty, farumadi_dynasty, gabras_dynasty, haciemirids_dynasty, hindu_dynasty, komnenos_dynasty, lusignan_dynasty, mulai_dynasty, qushji_dynasty, tadjeddinids_dynasty the
  Chinese text is shown with names respelled as the game and Phoenix spell them (English unchanged); and 20 descriptions are
  new, for Hellenized cultures that exist only in Phoenix.
- `main_menu/localization/*/oe_lde_rel_l_*.yml` and `in_game/localization/*/replace/zz_oe_lde_merge_l_*.yml`:
  for `greek_group_desc`, `hellenism_religion_desc`, `miaphysite_desc`, `nestorianism_desc`, `orthodox_desc`, `safavid_school_desc`, `shia_desc`, Phoenix keeps its own first paragraph where defined,
  preserves the paragraphs Descriptions Expanded added, and appends Phoenix's Batch 4 historical supplements for
  `miaphysite_desc`, `nestorianism_desc`, `orthodox_desc`, `safavid_school_desc`, `shia_desc`.

## Licence

- The Descriptions Expanded description texts are licensed under CC BY-SA 4.0 (upstream attribution preserved verbatim
  in `LICENSE`, `CREDITS.md` and `sources/sources.jsonl` here).
- Phoenix's additions listed above (the new descriptions and the merged paragraphs) are offered under CC BY-SA 4.0 as well.
  They were written for Phoenix with AI assistance from general historical knowledge and have not been checked line by
  line against sources.
- The rest of Phoenix is not covered by this folder; see the mod's own LICENSE.md.
