# Master Data Specification

For all of the following message specifications, the folder [master data examples](masterDataExamples) contains illustrative examples.

The underlying standards to express master data in B4L is [GS1 Smart Search](https://www.gs1.org/standards/gs1-smartsearch/1-6) in conjunction with [schema.org](https://schema.org/) and the [GS1 Web Vocabulary](https://www.gs1.org/gs1-web-vocabulary), the first external extension of schema.org.

Structured Data Testing Tool: https://search.google.com/structured-data/testing-tool

Note:
* URI prefix "gs1" expands to "https://gs1.org/voc/"
* URI prefix "schema" expands to "https://schema.org/"

## Party Master Data

| Data Element | Description |
| --- | -- |
| `context` | Dictionary |
| __`gs1` | "https://gs1.org/voc/" |
| __`xsd` | "https://www.w3.org/2001/XMLSchema#" |
| __`@vocab` | "https://gs1.org/voc/" |
| `@type` | `gs1:Organization` |
| `@id` | Canonical GS1 Digital Link URI `https://id.gs1.org/417/{Party GLN}` |
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
| `context` | Dictionary |
| __`gs1` | "https://gs1.org/voc/" |
| __`xsd` | "https://www.w3.org/2001/XMLSchema#" |
| __`@vocab` | "https://gs1.org/voc/" |
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

## Load Carrier Master Data

| Data Element | Description |
| --- | -- |
| `context` | Dictionary |
| __`dcterms` | "http://purl.org/dc/terms/" |
| __`foaf` | "http://xmlns.com/foaf/0.1/" |
| __`skos` | "http://www.w3.org/2004/02/skos/core#" |
| __`schema` | "http://schema.org/" |
| __`xsd` | "https://www.w3.org/2001/XMLSchema#" |
| `@type` | `schema:Thing` |
| `@id` | Canonical GS1 Digital Link URI `https://id.gs1.org/8003/{GRAI (without serial number)}` |
| `schema:identifier` | Dictionary |
| __`@type` | `PropertyValue` |
| ____`propertyID` | `https://www.gs1.org/standards/id-keys/grai` |
| ____`value` | `04012345111118` |
| `dcterms:title` | Load carrier name (`String`) |
| `dcterms:description` | List of 1...n dictionaries |
|  __`value` | Load carrier description (`String`)  |
|  __`language` | ISO 639-1 alpha-2 language code (`CodeValue`) |
| `skos:Concept` | Load carrier asset type (`CodeValue`) |
| `foaf:Document` | URL pointing to the load carrier's specification (`URL`) |

## Voucher Document Master Data

| Data Element | Description |
| --- | -- |
| `type` | `DigitalDocument` |
| `id` | Canonical GS1 Digital Link URI `https://id.gs1.org/253/{GDTI (without serial number)}` |
| `identifier` | `GDTI` (^\d{13}$) |
| `name` | Voucher document name (`String`) |
| `temporalCoverage` | Validity period (beginning with the date of creation of an instance), expressed as an ISO 8601 duration indicator with a year, month or day designator (`P[n]Y[n]M[n]D`) |
| `creator` | Canonical GS1 Digital Link URI `https://id.gs1.org/417/{Party GLN}` pointing to the owner of the GS1 Company Prefix with which GDTI is created |
