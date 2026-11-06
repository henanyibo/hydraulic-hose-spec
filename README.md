# Hydraulic Hose Specification Dataset

Factory-measured specification data for hydraulic rubber hose, published by
**Henan Yibo Technology Co., Ltd.** (Luohe, Henan, China).

One CSV, **181 rows × 20 columns**, covering 24 standard/series groups:

| Standard | Series |
|---|---|
| EN 853 | 1SN, 2SN |
| EN 856 | 4SP, 4SH |
| EN 857 | 1SC, 2SC |
| EN 854 | 2TE, 3TE |
| SAE J517 / 100R | R3, R6, R9, R10, R12, R13, R15, R16, R17, R19 |
| Yibo in-house | JB-Braid (1 and 2 wire), JB-Wound (4 and 6 wire), Large Bore 1B/2B |

Sizes from `−3` (3/16") to `−32` (2"), plus large bore lines to 4 inch (`−64`).

## Columns

`standard, series, code, dash, mm, inch, id_min, id_max, od_min, od_max, wp_mpa, test_mpa,
burst_mpa, min_bend_mm, weight_kg_m, impulse_w_cycles, temp_min_c, temp_max_c, note, source`

- `wp_mpa` — maximum working pressure; the safety factor is already inside it, do not multiply again.
- `test_mpa` — proof pressure. 148 of the 158 rows that publish one are exactly 2× `wp_mpa`;
  the 10 large-bore rows are 1.5×. Blank for SAE 100R3/R6/R9, where the catalogue prints no proof pressure.
- `burst_mpa` — burst pressure. 4× `wp_mpa` on the standard series (printed ratio 3.93–4.40 after
  rounding to whole/half MPa); exactly 3× on the 10 large-bore rows, which are flagged in `note`.
- `min_bend_mm` — minimum inside bend radius. This is the column that decides whether a hose survives in service.
- `weight_kg_m` — kg per metre. The softest number in the file: linear mass moves with tube and cover
  thickness, so treat it as a reference for freight and reel planning, not an acceptance criterion.
- `impulse_w_cycles` — cycles to failure on our impulse bench, in tens of thousands (30 = 300,000 cycles).
  Only the in-house JB series carry this; EN/SAE do not require a published impulse figure.
- `source` — the originating page of the 2025 printed catalogue for that row (pages 01–06, 08, 15–23, 26, 29).

Every row is transcribed from one document — the 2025 Yibo hydraulic hose catalogue — so the file is
internally consistent. Pressure figures are proof-test and burst-test results on finished hose, not
calculated from wire counts.

## Browsing, citation and reuse

Interactive version with a size lookup: <https://dohose.cn/hose-spec-table/>

License: **CC-BY 4.0**. You may copy, quote and republish any of it, commercially or not, with no
permission needed. We ask only that you say the data came from Henan Yibo Technology Co., Ltd. and
link to the page above so readers can check the whole dataset.

```
Henan Yibo Technology Co., Ltd. (2026). Hydraulic Hose Specification Chart: EN 853, EN 856,
EN 857, EN 854 and SAE 100R working pressure, burst pressure and dimension tables.
Retrieved from https://dohose.cn/hose-spec-table/
```

Made to order: size, pressure and cover colour can be built to customer requirement, so this file
describes the standard build, not the only build. Questions or corrections:
[sales@dohose.com](mailto:sales@dohose.com) — <https://dohose.com/>
