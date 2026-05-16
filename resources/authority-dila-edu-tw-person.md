---
title: "DILA Person Authority Database 人名規範資料庫"
created: 2026-04-18
updated: 2026-05-16
url: https://authority.dila.edu.tw/person/
language: zh
region: taiwan
tags:
- database
- buddhism
- digital_humanities
- religion
- taiwan
china_relevance: primary
source_id: authority-dila-edu-tw-person
description: "The DILA Person Authority Database provides authority records for people important to Buddhist studies, including names, variant names, biographical dates, roles, dynastic context, notes, and links to related place records. It has a documented JSONP data-provider API for lookup by authority ID or name string."
---
# DILA Person Authority Database 人名規範資料庫

**URL:** https://authority.dila.edu.tw/person/

**Language:** Chinese

**Region:** Taiwan

## Summary

The DILA Person Authority Database is part of the Buddhist Studies Authority Database Project maintained by Dharma Drum Institute of Liberal Arts. The larger project was created to integrate person, place, time, and Buddhist-catalogue data from DILA projects so that Buddhist digital resources can share stable identifiers and support cross-project searching.

The person database provides normalized records for figures relevant to Buddhist texts and Buddhist studies. Records may include an authority ID, authoritative name, variant names in Chinese or other languages, pinyin, gender, monastic status, role category, dynasty, birth and death date ranges, birth and death place references, short and full notes, and links to related DILA place authority records.

The search interface supports lookup by name, authority ID, old ID, notes, and life dates. The public search pages also surface recently added and recently updated records, high-frequency records, and entries with many alternative names. For researchers, the database is useful for entity disambiguation, prosopography, person-name authority control, Buddhist translation-history research, and linking names in texts to stable identifiers.

## API Access

DILA documents a public JSONP data-provider service for person records. The endpoint accepts either a DILA authority ID or a name string in the `id` parameter.

```text
https://authority.dila.edu.tw/webwidget/getAuthorityData.php?type=person&id=A000004&jsoncallback=cb
```

Parameters:

- `type=person` selects person authority records.
- `id=` accepts an authority ID such as `A000004` or a query string such as `鳩摩羅什`.
- `jsoncallback=` is required for the JSONP wrapper. The callback name is prepended to the returned JSON.

Example name lookup:

```text
https://authority.dila.edu.tw/webwidget/getAuthorityData.php?type=person&id=%E9%B3%A9%E6%91%A9%E7%BE%85%E4%BB%80&jsoncallback=cb
```

Returned fields can include `authorityID`, `name`, `class`, `gender`, `monk`, `bornDateBegin`, `bornDateEnd`, `diedDateBegin`, `diedDateEnd`, `note`, `noteFull`, `birthDateString`, `deathDateString`, `birthPlaceCode`, `birthPlaceName`, `deathPlaceCode`, `deathPlaceName`, `dynasty`, `names`, and `pinyin`.

Bulk data is also available from DILA's Open Content downloads as XML/TEI and RDF for the person authority database.
