---
title: "DILA Place Authority Database 地名規範資料庫"
created: 2026-04-18
updated: 2026-05-16
url: https://authority.dila.edu.tw/place/
language: zh
region: taiwan
tags:
- database
- buddhism
- digital_humanities
- geography
- gis
- religion
- taiwan
china_relevance: primary
source_id: authority-dila-edu-tw-place
description: "The DILA Place Authority Database provides normalized place records for Buddhist studies, including names, variant names, administrative context, coordinates, notes, and Buddhist textual references. It has a documented JSONP data-provider API for DILA-created place authority records."
---
# DILA Place Authority Database 地名規範資料庫

**URL:** https://authority.dila.edu.tw/place/

**Language:** Chinese

**Region:** Taiwan

## Summary

The DILA Place Authority Database is a Buddhist studies gazetteer and authority-control resource from Dharma Drum Institute of Liberal Arts. It belongs to the same Buddhist Studies Authority Database Project as the person, time, and Buddhist-catalogue databases, and is designed to support disambiguation, geospatial reference, and cross-project linking for Buddhist sources.

The search interface supports lookup by place name and authority ID, plus advanced filtering by administrative region and place category. Records may include a stable authority ID, authoritative name, variant names, pinyin, dynastic or name-type information, modern administrative location, historical district information, latitude and longitude, descriptive notes, and links useful for map-based display.

The database combines DILA-created place records with additional historical administrative place data licensed from Academia Sinica's Chinese Civilization in Time and Space project. This distinction matters for reuse: the online search interface can expose a broader set of records than the downloadable/API subset. For researchers, the database is useful for resolving place names in Buddhist texts, mapping Buddhist sites, connecting CBETA/DILA references to coordinates, and building geographic authority files for Chinese Buddhist studies.

## API Access

DILA documents a public JSONP data-provider service for place records. The API covers the DILA-created subset of place records; DILA notes that the API and downloads do not include the additional Academia Sinica-licensed records visible through the web search interface.

```text
https://authority.dila.edu.tw/webwidget/getAuthorityData.php?type=place&id=PL000000023253&jsoncallback=cb
```

Parameters:

- `type=place` selects place authority records.
- `id=` accepts a DILA place authority ID such as `PL000000023253`.
- `jsoncallback=` is required for the JSONP wrapper. The callback name is prepended to the returned JSON.

Although DILA's place API documentation describes ID lookup, the live endpoint also returns multiple matches for some name-string queries:

```text
https://authority.dila.edu.tw/webwidget/getAuthorityData.php?type=place&id=%E5%B5%A9%E5%B1%B1&jsoncallback=cb
```

Returned fields can include `authorityID`, `name`, `dynasty`, `long`, `lat`, `districtHistorical`, `districtModern`, `note`, `lang`, `shortAuthorityID`, `names`, `pinyin`, and sometimes merge information.

Bulk data is also available from DILA's Open Content downloads as XML/TEI and RDF for the place authority database.
