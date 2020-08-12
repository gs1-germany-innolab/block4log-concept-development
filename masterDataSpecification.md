# Master Data Specification

For all of the following message specifications, the folder [master data examples](masterDataExamples) contains illustrative examples.

The underlying standards to express master data in B4L is [GS1 Smart Search](https://www.gs1.org/standards/gs1-smartsearch/1-6) in conjunction with [schema.org](https://schema.org/) and the [GS1 Web Vocabulary](https://www.gs1.org/gs1-web-vocabulary), the first external extension of schema.org.

Structured Data Testing Tool: https://search.google.com/structured-data/testing-tool

Note:
* e.g. URI prefix "gs1" expands to "https://gs1.org/voc/"
* e.g. URI prefix "schema" expands to "https://schema.org/"

## Party Master Data

| Data Element | Description | Mandatory |
| --- | --- | --- |
| `context` | Dictionary | x |
| __`gs1` | "https://gs1.org/voc/" | x |
| __`@vocab` | "https://gs1.org/voc/" | x |
| `@type` | `gs1:Organization` | x |
| `@id` | Canonical GS1 Digital Link URI `https://id.gs1.org/417/{Party GLN}` | x |
| `globalLocationNumber` | `GLN` (^\d{13}$) | x |
| `organizationName` | List of 1...n dictionaries | x |
| __`value` | Organisation name (`String`) | x |
| __`language` | ISO 639-1 alpha-2 language code (`CodeValue`) | x |
| `address` | List of 1...n dictionaries | x |
| __`streetAddress` | List of 1...n dictionaries | x |
| ____`value` | Street name and number (`String`) | x |
| ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) | x |
| __`addressLocality` | List of 1...n dictionaries | x |
| ____`value` | City (`String`) | x |
| ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) | x |
| __`postalCode` | Postal or zip code  (`String`) | x |
| __`addressCountry` | Dictionary | x |
| ____`countryCode` | ISO 3166-1 alpha-2 country code (`CodeValue`) | x |
| ____`type` | `gs1:Country` | x |
| __`type` | `gs1:PostalAddress` | x |

Note: At the least, organizationName and address information MUST be provided in English. Providing party master data in further languages is possible though.

## Location Master Data

| Data Element | Description | Mandatory |
| --- | --- | --- |
| `context` | Dictionary | x |
| __`gs1` | "https://gs1.org/voc/" | x |
| __`@vocab` | "https://gs1.org/voc/" | x |
| `type` | `gs1:Place` | x |
| `id` | Canonical GS1 Digital Link URI `https://id.gs1.org/414/{Physical Location GLN}` | x |
| `globalLocationNumber` | `GLN` (^\d{13}$) | x |
| `address` | List of 1...n dictionaries | x |
| __`organizationName` | List of 1...n dictionaries | x |
| ____`value` | Site/location name (`String`) | x |
| ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) | x |
|  __`streetAddress` | List of 1...n dictionaries | x |
|  ____`value` | Street name and number (`String`) | x |
|  ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) | x |
|  __`addressLocality` | List of 1...n dictionaries | x |
|  ____`value` | City (`String`) | x |
|  ____`language` | ISO 639-1 alpha-2 language code (`CodeValue`) | x |
|  __`postalCode` | Postal or zip code  (`String`) | x |
|  __`addressCountry` | Dictionary | x |
|  ____`countryCode` | ISO 3166-1 alpha-2 country code (`CodeValue`) | x |
|  ____`type` | `gs1:Country` | x |
|  __`type` | `gs1:PostalAddress` | x |

Note: At the least, address information MUST be provided in English. Providing location master data in further languages is possible though.

## Load Carrier Master Data

| Data Element | Description | Mandatory |
| --- | --- | --- |
| `context` | Dictionary | x |
| __`dcterms` | "http://purl.org/dc/terms/" | x |
| __`foaf` | "http://xmlns.com/foaf/0.1/" | x |
| __`skos` | "http://www.w3.org/2004/02/skos/core#" | x |
| __`schema` | "http://schema.org/" | x |
| __`xsd` | "https://www.w3.org/2001/XMLSchema#" | x |
| `@type` | `schema:Thing` | x |
| `@id` | Canonical GS1 Digital Link URI `https://id.gs1.org/8003/{GRAI (without serial number)}` | x |
| `schema:identifier` | Dictionary | x |
| __`@type` | `PropertyValue` | x |
| ____`propertyID` | `https://www.gs1.org/standards/id-keys/grai` | x |
| ____`value` | `GRAI` (^\d{14}$) | x |
| `dcterms:title` | List of 1...n dictionaries | x |
|  __`value` | Load carrier name (`String`)  | x |
|  __`language` | ISO 639-1 alpha-2 language code (`CodeValue`) | x |
| `gs1:manufacturer` | Dictionary | TBD |
| __`@type` | `gs1:Organization` |  |
| __`@id` | Canonical GS1 Digital Link URI `https://id.gs1.org/417/{Party GLN}` |  |
| `dcterms:description` | List of 1...n dictionaries | x |
|  __`value` | Load carrier description (`String`)  | x |
|  __`language` | ISO 639-1 alpha-2 language code (`CodeValue`) | x |
| `schema:image` | Web URI pointing to the load carrier's image (`URL`) | TBD |
| `gs1:netWeight` | Dictionary | TBD |
| __`gs1:value` | Dictionary |   |
| ____`@:value` | Quantitative value of the load carrier's net weight (`float`) |
| ____`@:type` | `xsd:float` |   |
| __`gs1:unitCode` | Measurement Unit according to UN/ECE Recommendation 20 (e.g. `KGM` for kilogram) |  |
| __`@:type` | `gs1:QuantitativeValue` |  |
| `gs1:grossWeight` | Dictionary | TBD |
| __`gs1:value` | Dictionary |   |
| ____`@:value` | Quantitative value of the load carrier's gross weight (`float`) |
| ____`@:type` | `xsd:float` |  |
| __`gs1:unitCode` | Measurement Unit according to UN/ECE Recommendation 20 (e.g. `KGM` for kilogram) |  |
| __`@:type` | `gs1:QuantitativeValue` |  |
| `schema:width` | Dictionary | TBD |
| __`schema:value` | Dictionary |   |
| ____`@:value` | Quantitative value of the load carrier's width (`float`) |
| ____`@:type` | `xsd:float` |  |
| __`schema:unitCode` | Measurement Unit according to UN/ECE Recommendation 20 (e.g. `MMT` for millimetre) |  |
| __`@:type` | `schema:QuantitativeValue` |  |
| `schema:depth` | Dictionary | TBD |
| __`schema:value` | Dictionary |   |
| ____`@:value` | Quantitative value of the load carrier's depth (`float`) |
| ____`@:type` | `xsd:float` |  |
| __`schema:unitCode` | Measurement Unit according to UN/ECE Recommendation 20 (e.g. `MMT` for millimetre) |  |
| __`@:type` | `schema:QuantitativeValue` |  |
| `schema:height` | Dictionary | TBD |
| __`schema:value` | Dictionary |   |
| ____`@:value` | Quantitative value of the load carrier's height (`float`) |
| ____`@:type` | `xsd:float` |  |
| __`schema:unitCode` | Measurement Unit according to UN/ECE Recommendation 20 (e.g. `MMT` for millimetre) |  |
| __`@:type` | `schema:QuantitativeValue` |  |
| `gs1:colourCode` | Dictionary | TBD |
| __`gs1:colourCodeValue` | PANTONE Color Code (`String`) |  |
| __`gs1:colourCodeList` | Dictionary |  |
| ____`@type` | `https://www.gs1.org/voc/ColourCodeListCode` |  |
| ____`@:id` | `xsd:float` | Color Code List according to https://www.gs1.org/voc/ColourCodeListCode (`CodeValue`) |
| __`@type` | `gs1:ColourCodeDetails` |  |
| `skos:Concept` | Load carrier asset type (`CodeValue`) | x |
| `foaf:Document` | URL pointing to the load carrier's specification (`URL`) | TBD |

Note: At the least, title and description MUST be provided in English. Providing load carrier master data in further languages is possible though.

## Voucher Document Master Data

| Data Element | Description |
| --- | -- |
| `type` | `DigitalDocument` |
| `id` | Canonical GS1 Digital Link URI `https://id.gs1.org/253/{GDTI (without serial number)}` |
| `identifier` | `GDTI` (^\d{13}$) |
| `name` | Voucher document name (`String`) |
| `temporalCoverage` | Validity period (beginning with the date of creation of an instance), expressed as an ISO 8601 duration indicator with a year, month or day designator (`P[n]Y[n]M[n]D`) |
| `creator` | Canonical GS1 Digital Link URI `https://id.gs1.org/417/{Party GLN}` pointing to the owner of the GS1 Company Prefix with which GDTI is created |


## Open Questions
* Do we need a version/last updated attribute for each of the above master data sets?
