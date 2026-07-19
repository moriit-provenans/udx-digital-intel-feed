# UDX Digital Intelligence Hub — Public Feed

Atlas（Data Lake）が収集・更新する **海外デジマ実行指標** の公開 JSON。
Smith が udx.co.jp `/intel/` に同期する。

| | |
|---|---|
| **Owner** | Atlas（moriit-provenans） |
| **Consumer** | Smith / UDX |
| **Req** | REQ-SMITH-20260718-003 |
| **Schema** | PROVE timeseries v2 同型 + `track: A\|B\|Both` |
| **Cadence** | Trends 週次 / EF EPI 年次 / WB・ITU（PROVE reuse）月次想定 |
| **Status** | Phase 1 MVP seed（2026-07-19） |

## Layout

- `_manifest.json` / `_catalog.json` / `_health.json` / `as_of_manifest.json`
- `timeseries/*.json`
- `schema/observation.schema.json`

## Live metrics (MVP)

| metric_id | source |
|---|---|
| udx.infra.internet_penetration | PROVE feed reuse (WB IT.NET.USER.ZS) |
| udx.infra.mobile_subscriptions | PROVE feed reuse |
| udx.infra.fixed_broadband | PROVE feed reuse |
| udx.macro.gdp_nominal / gdp_per_capita / population / urban_population_pct | PROVE feed reuse |
| udx.lang.business_languages | static JSON |
| udx.lang.ef_epi | EF EPI 2025 via Wikipedia（117 geos） |
| udx.search.trends_*_jp (3) | Google Trends / pytrends |

## Notes

- No private secrets in this public repo.
- PROVE source: https://github.com/moriit-provenans/prove-global-data-hub-feed
- Trends: Trends slot kept prior seed / skipped (all trends failed or blocked; detail={'udx.search.trends_multilang_seo_jp': "fail:TypeError:Retry.__init__() got an unexpected keyword argument 'method_whitelist'", 'udx.search.trends_ma_cdp_jp': "fail:TypeError:Retry.__init__() got an unexpected keyword argument 'method_whitelist'", 'udx.search.trends_llmo_jp': "fail:TypeError:Retry.__init__() got an unexpected keyword argument 'method_whitelist'"})
- Planned next: StatCounter browser/OS、国別 e-commerce Trends、○指標（広告・SNS等）

## Fail-safe (Smith UI)

最終更新バナー・古い `as_of_date` の非表示は Smith `/intel/` 側。
