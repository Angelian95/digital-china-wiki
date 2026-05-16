---
title: "DILA Authority Database of Buddhist Tripitaka Catalogues 佛經目錄規範資料庫"
created: 2026-04-18
updated: 2026-05-16
url: https://authority.dila.edu.tw/catalog/
language: zh
region: taiwan
tags:
- bibliography
- buddhism
- catalog
- database
- digital_humanities
- religion
- taiwan
china_relevance: primary
source_id: authority-dila-edu-tw-catalog
description: "The DILA Authority Database of Buddhist Tripitaka Catalogues normalizes Buddhist textual catalogue data around CBETA, historical catalogues, modern scholarship, person records, place records, and time records. Its web search supports title, authority ID, CBETA number, author/translator, completion place, and completion date; the same DILA data-provider endpoint also returns JSONP catalog records."
---
# DILA Authority Database of Buddhist Tripitaka Catalogues 佛經目錄規範資料庫

**URL:** https://authority.dila.edu.tw/catalog/

**Language:** Chinese

**Region:** Taiwan

## Summary

The DILA Authority Database of Buddhist Tripitaka Catalogues is a bibliographic authority resource for Buddhist texts and catalogues. DILA describes the project as a reconstruction and integration of Buddhist catalogue data based on CBETA texts, historical catalogues, modern research, and the other DILA authority databases, forming a reference database that links texts, people, places, and dates.

The search interface supports lookup by title string, authority ID, CBETA text number, author or translator, completion place, and completion date. Records can include DILA catalogue authority IDs, CBETA numbers, text titles, fascicle counts, character counts, volume information, bylines, author or translator authority links, date evidence from different sources, translation descriptions, witness information, related texts, CBC@ links, and topical or canonical categories.

The database draws on sources such as Taisho catalogue materials, Korean Buddhist Canon catalogue data, CBETA, CBETA Metadata, and the Chinese Buddhist Canonical Attributions database. Its public search page also provides useful aggregate views: works by author/translator, works by completion place, and works by historical period. This makes it valuable for Buddhist bibliography, canon-history research, translation attribution, CBETA-linked text identification, and digital humanities work that needs stable identifiers for Buddhist textual works.

## API Access

The DILA services documentation found for the authority project explicitly documents person, place, and date queries. It does not appear to document a separate catalog-query page in the same way. However, the live `getAuthorityData.php` endpoint currently returns catalog records when called with `type=catalog`.

Lookup by DILA catalogue authority ID:

```text
https://authority.dila.edu.tw/webwidget/getAuthorityData.php?type=catalog&id=CA0000015&jsoncallback=cb
```

Lookup by CBETA number:

```text
https://authority.dila.edu.tw/webwidget/getAuthorityData.php?type=catalog&id=T0366&jsoncallback=cb
```

Parameters:

- `type=catalog` selects Buddhist catalogue records.
- `id=` accepts a DILA catalogue authority ID such as `CA0000015` or a CBETA number such as `T0366`.
- `jsoncallback=` wraps the returned data as JSONP.

Returned fields observed from the live endpoint include `authority_id`, `jing_title`, `juan`, `char_count`, `cbeta_id`, `vol`, `byline`, `jing_no`, `editors`, `dates`, `transdesc`, `wit`, `sameas`, `cbc_links`, `related_jings`, and `category`.

Because the catalog API behavior is live but less clearly documented than the person and place APIs, users should verify endpoint behavior before depending on it for production workflows. For broader or reproducible catalogue-data work, also check DILA's documentation links to CBETA Metadata and related catalogue data sources.
