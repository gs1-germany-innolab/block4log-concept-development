# Asset Type Code

## Purpose
Load Carrier Exchange Events and Dept Tokens in B4L accommodate IDs (typically a Global Returnable Asset Identifier) identifying a specific load carrier (e.g. a EUR pallet or a specific reusable tray of a closed pool system).
In open pool systems, a given load carrier can be manufactured/commissioned by several parties. Thus, one and the same asset type can have different GRAIs.
To enable trading of assets of the same asset type, a GRAI needs to be related to its corresponding asset type which in turn is based on a controlled vocabulary/code value list.

In B4L, we intend to make this list available as linked open vocabulary. In other words, each code value is resolvable through the Web.

At this moment of time, there is no globally standardised code list available (such as for many other domains, e.g. https://gs1.org/voc/ConsumerLifestageCode). Against this background, we need to specify an own code list which, for the time being, is B4L specific, but might be superseded by a global standard in the future (e.g. as part of the GS1 Web Vocabulary, see https://www.gs1.org/voc/).

tbc:`CodeValue` expands to: https://{domain/sub domain name tbd}/`CodeValue`

## Code Value List

| Code Value | Name | Description and URI |
| --- | --- | ---|
| `E_1_PERFORMANCE_TRAY` | E1 Performance Tray | Reusable meat tray 'E Performance 1' according to GS1 Germany Type Specification `tbd:E_1_PERFORMANCE_TRAY` |
| `E_2_PERFORMANCE_TRAY` | E2 Performance Tray | Reusable meat tray 'E Performance 2' according to GS1 Germany Type Specification `tbd:E_2_PERFORMANCE_TRAY` |
| `E_3_PERFORMANCE_TRAY` | E3 Performance Tray | Reusable meat tray 'E Performance 3' according to GS1 Germany type specification `tbd:E_3_PERFORMANCE_TRAY` |
| `EUR_1_PALLET` | EUR 1 | Euro-pallet 'EUR 1' according to European Pallet Association (EPAL) specification `tbd:EUR_1_PALLET` |
| `EUR_2_PALLET` | EUR 2 | Euro-pallet 'EUR 2' according to European Pallet Association (EPAL) specification `tbd:EUR_2_PALLET` |
| `EUR_3_PALLET` | EUR 3 | Euro-pallet 'EUR 3' according to European Pallet Association (EPAL) specification `tbd:EUR_3_PALLET` |
| `EUR_6_PALLET` | EUR 6 | Euro-pallet 'EUR 6' according to European Pallet Association (EPAL) specification `tbd:EUR_6_PALLET` |