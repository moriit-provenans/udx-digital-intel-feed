# UDX Digital Intelligence Hub — Public Feed

Atlas（Data Lake）が収集・更新する **海外デジマ実行指標** の公開 JSON。
Smith が udx.co.jp `/intel/` に同期する。

| | |
|---|---|
| **Owner** | Atlas（moriit-provenans） |
| **Consumer** | Smith / UDX |
| **Req** | REQ-SMITH-20260718-003 |
| **Schema** | PROVE timeseries v2 同型 + `track: A|B|Both` |
| **Cadence** | Phase1 以降・週次想定 |

## Layout

- `_manifest.json` / `_catalog.json` / `_health.json` / `as_of_manifest.json`
- `timeseries/*.json`
- `schema/observation.schema.json`

## Status

Phase 0 triage 完了（2026-07-18）。Phase 1 = ◎指標から順次投入。
