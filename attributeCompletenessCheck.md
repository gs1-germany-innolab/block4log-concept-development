# Attribute completeness check

## Purpose
* Control whether B4L data structures accommodate all required attributes identified by the process group
* Identify ambiguities/subjects for discussion with process/governance sub group

Source: B4L User Stories V1 2020-06-17, column I (deduced requirement)

## Check list

| # | Requirement | Covered in/ via | Questions + comments | CHECK |
| --- | --- | --- | --- | --- |
| CLOSED | POOLS |
| 1 | After completion of the pallet exchange, a data record describing the exchange process is available on the block chain | EPCIS Event | Data record: yes. TBD, whether on BC | `DONE` |
| 2 | The loader receives a legally valid confirmation after the pallet exchange has been completed  |   | n./a. (no attribute)  | `DONE` |
| 3 | The number of pallets taken over and transferred is documented in the block chain  |  EPCIS Event, quantity element (ID + number) |   | `DONE` |
| 4 | When the pallets are handed over a transaction is triggered by the loader / office goods issue  | EPCIS Event  | n./a. (no attribute)  | `DONE` |
| 5 | The transaction on the block chain can be selected  |   | n./a. (no attribute)  | `DONE` |
| 6 | The pallet account is identified by the GLN  | EPCIS Event, source/ destination (PGLN)  |   | `DONE` |
| 7 | The office goods issue / loader creates a transaction with the following attributes: Place of issue, issuer, exchange partner, GDTI, GRAI/pallet type, quantity, (quality), date, vehicle registration number, transaction (inbound/outbound), reason for comment, reference number,  (Recipient of LC), (Consignor of LC)  | EPCIS Event, readPoint (SGLN), source/ destination (PGLN), bizTransaction List (palletNote, GDTI), quantityElement, qualityLevel, eventTime, bizStep (arriving/ departing)  | TBD: reference number, reason (free text), vehicle registration number  | `OPEN`  |
| 8 | After loading, the driver can check and confirm the quantity (and quality) of loaded pallets, if necessary note a reservation   |   |  n./a. (no attribute) | `DONE` |
| 9 | Information is contained in the BC transaction, stock information is not generated from the BC  |   | n./a. (no attribute)  | `DONE` |
| 10 | When pallets are delivered, the Goods Receipt/Loader office can confirm the quantity (and quality) of delivered pallets to the driver  | EPCIS Event, quantityElememt, qualityLevel  |   | `DONE` |
| 11 | The office goods receipt has a documentation on the block chain after processing |   |   n./a. (no attribute) | `DONE` |
| 12 | The pallet notes are booked completely and the account balance is displayed correctly  |   |  n./a. (no attribute) | `DONE` |
| 13 | Similar to 7  |   |   | `OPEN` |
| 14 | Similar to 1  |   |   | `DONE` |
| 15 | Similar to 3  |   |   | `DONE` |
| 16 | Corrections can be initiated and approval of the exchange partner is requested  |  EPCIS Event, Error Declaration Element |   | `DONE` |
| OPEN | POOLS |
| 17 | Similar to 1  |   |   | `DONE` |
| 18 | Similar to 2  |   |   | `DONE` |
| 19 | Similar to 3  |   |   | `DONE` |
| 20 | Similar to 4  |   |   | `DONE` |
| 21 | Similar to 5  |   |   | `DONE` |
| 22 | Similar to 6  |   |   | `DONE` |
| 23 | Similar to 7  |   |   | `OPEN` |
| 24 | Similar to 8  |   |   | `DONE` |
| 25 | Similar to 9  |   |   | `DONE` |
| 26 | Similar to 10  |   |   | `DONE` |
| 27 | Similar to 11  |   |   | `DONE` |
| 28 | Similar to 12  |   |   | `DONE` |
| 29 | Similar to 7  |   |   | `OPEN` |
| 30 | Similar to 1  |   |   | `DONE` |
| 31 | The quantity of pallets taken over and handed over is documented in the block chain and confirmed by the driver  | EPCIS Event, quantity element (ID + number)  |   | `DONE` |
| 32 | The pallet exchange is completely documented & booked (incl. reservations). The account balance is displayed correctly by GLN |   | What does 'incl. reservations' means? | `OPEN` |
| 33 | After the pallet exchange has been carried out, the resulting account changes are correctly displayed  |   | n./a. (no attribute) | `DONE` |
| 34 | Similar to 16  |   |   |   |
| 35 | It will not be possible to deduce a stock view from BC  |   | n./a. (no attribute)  | `DONE` |
| 36 | The pallet dispatcher has access to the exchange partner pallet accounts  |   | n./a. (no attribute) | `DONE` |
| 37 | Similar to 32  |   |   | `OPEN` |


## ToDos:
* Add other transactions to column 'Covered in /via', in which data attributes appear 