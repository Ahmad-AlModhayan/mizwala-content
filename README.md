# Mizwala content

Files the Mizwala app (a free Quran, prayer-times and adhkar app for Android, no ads, no accounts, no tracking)
downloads only when a reader asks for them. Nothing here is fetched otherwise.

## Tafsir (release `tafsir-1`)

Three tafsir editions, each a small read-only SQLite database, gzipped. The app checks each download against the
SHA-256 it ships with before installing it.

| File | Edition | Download | Installed |
|---|---|---|---|
| `muyassar.db.gz` | التفسير الميسّر, King Fahad Glorious Quran Printing Complex | 0.7 MB | 2.5 MB |
| `mukhtasar.db.gz` | المختصر في تفسير القرآن الكريم, Tafsir Center for Quranic Studies | 0.7 MB | 2.3 MB |
| `tabari.db.gz` | جامع البيان عن تأويل آي القرآن, Ibn Jarir al-Tabari | 8.5 MB | 40.6 MB |

SHA-256:

```
a74ac00bb14bf7ccc97b52952abafeb7fc59fd6a6fcdbe76877e4e1deab9c7f5  muyassar.db.gz
ce788952cb0e5b2073b4b946c8f76ead129f980db709d1a0f199ab58d851cc8b  mukhtasar.db.gz
7b87b6710458a6fac3ae7de46f1d6ed1f3dfe2dcf78d7557ec33ad5f903e8f56  tabari.db.gz
```

### Source and credit

The texts come from the [Quranic Universal Library](https://qul.tarteel.ai) (Tarteel). Mizwala's owner asked QUL's
staff about using them in a free app, and they had no objection. The texts are kept as published; only the HTML
markup is reduced to headings, paragraphs and marked Quranic quotations, which the app shows in a Quran font,
unaltered.

Credit for each edition belongs to its authors and publishers named above. Each file is redistributed here, free
of charge, only so the app can offer it on request. If you are a rights holder and want a file removed, open an
issue and it will be taken down.

These editions are not Kahf Labs' work, and this repository grants no licence over them. They are shared here only
so the Mizwala app can offer them on request. To use them for anything else, go to the source above and its rights
holders.

### Format

```
meta(key, value)                                   id, name, format (1), source
ayah(id INTEGER PRIMARY KEY, grp)                  surah * 1000 + ayah → its group
grp(id INTEGER PRIMARY KEY, first, last, body)     one text explaining ayahs first..last
```

`body` uses only `<h>`, `<p>` and `<q>` (a quotation of the Quran), with `&amp; &lt; &gt;`. Built by
`tools/build_tafsir.py` in the app's repository.
