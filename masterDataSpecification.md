# Master Data Specification

For all of the following message specifications, the folder [master data examples](masterDataExamples) contains illustrative examples.

The underlying standards to express master data in B4L is [GS1 Smart Search](https://www.gs1.org/standards/gs1-smartsearch/1-6) in conjunction with the [GS1 Web Vocabulary](https://www.gs1.org/gs1-web-vocabulary), the first official extension to [Schema.org](https://schema.org/).

Note: the URI prefix "gs1" expands to "https://gs1.org/voc/"

## Party Master Data

| Data Element | Description |
| --- | -- |
| `type` | `gs1:Organization` |
| `id` | Canonical GS1 Digital Link URI `https://id.gs1.org/417/{Party GLN}` |
| `globalLocationNumber` | `GLN` (^\d{13}$) |
| `organizationName` | List of 1...n dictionaries |
| __`value` | Organisation name (`String`) |
| __`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
| `address` | List of 1...n dictionaries |
| __`streetAddress` | List of 1...n dictionaries |
| ____`value` | Street name and number (`String`) |
| ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
| __`addressLocality` | List of 1...n dictionaries |
| ____`value` | City (`String`) |
| ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
| __`postalCode` | Postal or zip code  (`String`) |
| __`addressCountry` | Dictionary |
| ____`countryCode` | ISO 3166-1 alpha-2 country code (`CodeValue`) |
| ____`type` | `gs1:Country` |
| __`type` | `gs1:PostalAddress` |

## Location Master Data

| Data Element | Description |
| --- | -- |
| `type` | `gs1:Place` |
| `id` | Canonical GS1 Digital Link URI `https://id.gs1.org/414/{Physical Location GLN}` |
| `globalLocationNumber` | `GLN` (^\d{13}$) |
| `address` | List of 1...n dictionaries |
| __`organizationName` | List of 1...n dictionaries |
| ____`value` | Site/location name (`String`) |
| ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
|  __`streetAddress` | List of 1...n dictionaries |
|  ____`value` | Street name and number (`String`) |
|  ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
|  __`addressLocality` | List of 1...n dictionaries |
|  ____`value` | City (`String`) |
|  ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
|  __`postalCode` | Postal or zip code  (`String`) |
|  __`addressCountry` | Dictionary |
|  ____`countryCode` | ISO 3166-1 alpha-2 country code (`CodeValue`) |
|  ____`type` | `gs1:Country` |
|  __`type` | `gs1:PostalAddress` |