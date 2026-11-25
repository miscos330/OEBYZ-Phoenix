# Third-Party Provenance & Attribution Ledger — Project Phoenix v31.0 WP35

All gameplay scripts, localizations, and visual assets in WP35 (`oe_wp35_*`) are generated reproducibly by `gen_v310_wp35_great_powers_and_diplomacy.py` with **zero vanilla overrides** and **zero modifications** to pre-existing Project Phoenix files.

## Authorized Upstream Sources

1. **Rise of the British Empire** (EU5 Steam Workshop `3621489583`) — Design & native EU5 1.4.9 basis for the 53-task British Imperial mission tree (`oe_wp35_bri_missions`), the East India Company Situation (`oe_wp35_eic_situation`) + custom panel UI + native `?` play guide (`scriptable_hints`), 6 Indian purchase/lease/charter/dominion diplomatic actions, 2 situation actions, and complete Simplified Chinese localization.
2. **Subjects Expanded** (EU4 Steam Workshop `1834079712`) & **Governments Expanded** (EU4 Steam Workshop `1596815683`) — Conceptual inspiration rebuilt 100% natively in EU5 1.4.9 for 5 subject diplomatic interactions (`oe_wp35_subj_*`) and 9 bilateral industry trade treaties (`oe_wp35_treaty_*`).
3. **Flavor & Events Expanded (FEE)** (EU4 Steam Workshop `2185445645`) — Conceptual inspiration rebuilt 100% natively in EU5 1.4.9 for the 4-track Cato Royal Heir Education curriculum (`oe_wp35_cato.*`) and 3 Rival Great Power Crisis Disasters (Ottoman Imperial Decline, Habsburg Dual Succession Stress, Polish Magnate Partition Crisis).
4. **Great Ming 200 Provinces** (EU4 Steam Workshop `2187691560`) — Historical inspiration & 7 verified 2D monument DDS icons for the 7 Famous Chinese Academies & Ancient Temples (`oe_wp35_ming_*`) placed on verified EU5 1.4.9 Chinese locations (`changsha`, `xingzi`, `dengfeng`, `suiyang_guide`, `luoyang`, `qufu`).
5. **RICE — Regional Immersion & Cultural Enrichment** (CK3 Steam Workshop `2273832430`) — Historical inspiration & 4 verified Eastern Mediterranean scene DDS illustrations for 5 Mediterranean flavor arcs (`oe_wp35_rice_*`: Chios Mastic Monopoly, Rhodes Hospitaller Commerce, Lesbos Gattilusi Patronage, Coptic Alexandrian Heritage, Armenian Cilician Guilds).

## Strict Asset Exclusions

- Commercial / unlicensed third-party packs (including EU4 Workshop `694484401` AAU DLC pictures and `2829397295` Osprey art) and all `.ogg`/`.mp3`/`.wav` audio tracks are **strictly excluded**.
- Every vaulted `.dds` asset below has been verified for a valid 128-byte DDS header (`DDS ` magic + 124-byte `DDS_HEADER`).

## Vaulted DDS Assets (14 files)

| Vault Relative Path | Dimensions | FourCC | Size (B) | SHA-256 (16) | Upstream Source |
|---|---|---|---:|---|---|
| `main_menu/gfx/interface/advance/oe_wp35_bri_hundred_years_war.dds` | 59x63 | `DXT5` | 4224 | `e9a8f6255cbba08c` | EU5 Workshop 3621489583 (Rise of the British Empire) (`mission_hundred_years_war.dds`) |
| `main_menu/gfx/interface/icons/situations/oe_wp35_eic_situation.dds` | 128x128 | `DXT5` | 22000 | `eb555780bba61d89` | EU5 Workshop 3621489583 (Rise of the British Empire) (`gb_company_in_india.dds`) |
| `main_menu/gfx/interface/illustrations/situation/oe_wp35_eic_situation.dds` | 1080x440 | `DXT1` | 317512 | `7a6e7d051f892e85` | EU5 Workshop 3621489583 (Rise of the British Empire) (`gb_company_in_india.dds`) |
| `main_menu/gfx/interface/icons/buildings/oe_wp35_ming_yuelu_hall.dds` | 300x150 | `DXT5` | 45728 | `bb717c81d2b04e77` | EU4 Workshop 2187691560 (Great Ming 200 Provinces) (`yuelushuyuan.dds`) |
| `main_menu/gfx/interface/icons/buildings/oe_wp35_ming_bailudong_academy.dds` | 300x150 | `DXT5` | 45728 | `ddc6f594ad08c0ac` | EU4 Workshop 2187691560 (Great Ming 200 Provinces) (`bailudongshuyuan.dds`) |
| `main_menu/gfx/interface/icons/buildings/oe_wp35_ming_songyang_academy.dds` | 300x150 | `DXT5` | 45728 | `f6bd588bc1deda4e` | EU4 Workshop 2187691560 (Great Ming 200 Provinces) (`songyangshuyuan.dds`) |
| `main_menu/gfx/interface/icons/buildings/oe_wp35_ming_yingtianfu_academy.dds` | 300x150 | `DXT5` | 45728 | `b9dcd8db26a976fd` | EU4 Workshop 2187691560 (Great Ming 200 Provinces) (`yingtianshuyuan.dds`) |
| `main_menu/gfx/interface/icons/buildings/oe_wp35_ming_shaolin_temple.dds` | 300x148 | `DXT5` | 44528 | `aea78dcfb66e223b` | EU4 Workshop 2187691560 (Great Ming 200 Provinces) (`shaolinsi.dds`) |
| `main_menu/gfx/interface/icons/buildings/oe_wp35_ming_baima_temple.dds` | 300x148 | `DXT5` | 44528 | `20d24e5d8b6eb7db` | EU4 Workshop 2187691560 (Great Ming 200 Provinces) (`baimasi.dds`) |
| `main_menu/gfx/interface/icons/buildings/oe_wp35_ming_qufu_kongmiao.dds` | 300x150 | `DXT5` | 45728 | `126df1ff5c93fac9` | EU4 Workshop 2187691560 (Great Ming 200 Provinces) (`kongmiao.dds`) |
| `main_menu/gfx/interface/illustrations/events/oe_wp35_rice_chios_mastic.dds` | 1500x842 | `DXT1` | 633128 | `14f9027e9d33c308` | CK3 Workshop 2273832430 (RICE — Regional Immersion & Cultural Enrichment) (`RICE_chios_mastic_grove.dds`) |
| `main_menu/gfx/interface/illustrations/events/oe_wp35_rice_rhodes_commerce.dds` | 1500x842 | `DXT1` | 633128 | `bc37b2189649ed92` | CK3 Workshop 2273832430 (RICE — Regional Immersion & Cultural Enrichment) (`RICE_rhodes_castle.dds`) |
| `main_menu/gfx/interface/illustrations/events/oe_wp35_rice_lesbos_gattilusi.dds` | 1500x842 | `DXT1` | 633128 | `6a013ebc7cc4756e` | CK3 Workshop 2273832430 (RICE — Regional Immersion & Cultural Enrichment) (`RICE_lesbos_island.dds`) |
| `main_menu/gfx/interface/illustrations/events/oe_wp35_rice_coptic_alexandria.dds` | 1110x440 | `DXT1` | 244768 | `5ed7ab986623eed0` | CK3 Workshop 2273832430 (RICE — Regional Immersion & Cultural Enrichment) (`activity_RICE_coptic_saint_anthony_pilgrimage.dds`) |
