# Master Data Specification

For all of the following message specifications, the folder [master data examples](masterDataExamples) contains illustrative examples.

The underlying standards to express master data in B4L is [GS1 Smart Search](https://www.gs1.org/standards/gs1-smartsearch/1-6) in conjunction with the [GS1 Web Vocabulary](https://www.gs1.org/gs1-web-vocabulary), the first official extension to [Schema.org](https://schema.org/).

Note: the URI prefix "gs1" expands to "https://gs1.org/voc/"

## Party Master Data

| Data Element | Description |
| --- | -- |
| `type` | `gs1:Organization` |
| `id` | Canonical GS1 Digital Link URI `https://id.gs1.org/417/{Party GLN}` |
| `organizationName` | List of 1...n dictionaries |
|  __`value` | Organisation name (`String`) |
|  __`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
| `globalLocationNumber` | `GLN` (^\d{13}$) |
| `address` | List of 1...n dictionaries |
|  __`streetAddress` | List of 1...n dictionaries |
|  ____`value` | Street name and number (`String`) |
|  ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
|  __`addressLocality` | List of 1...n dictionaries |
|  ____`value` | City (`String`) |
|  ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
|  __`countyCode` | ISO 3166-1 alpha-2 country code (`CodeValue`) |
|  __`postalCode` | postal or zip code  (`String`) |
|  __`type` | `gs1:PostalAddress`) |