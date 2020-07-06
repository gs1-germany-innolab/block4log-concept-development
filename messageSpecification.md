# Message Specification

| Dim | Data Element | V1 | V2 |
| --- | ------------ | -- | -- | 
|  | Description | RTIs arrive at a given location | RTIs leave a given location |
|  | Event Type | Object Event | Object Event | 
|  | Action | OBSERVE | OBSERVE | 
| When | `eventTime` | 15 June, 08:00 am | 15 June, 08:15 am | 
| What | `quantityList` - `quantityElement` |
|  |  `epcClass` | `GRAI` (without serial number) of RTI | `GRAI` (without serial number) of RTI |
|  |  `quantity` | Number of arrived RTIs | Number of departed RTIs |
| Where | `readPoint` | `SGLN` (without GLN extension) of RTI exchange location | `SGLN` (without GLN extension) of RTI exchange location |
| Why | `bizStep` | `Arriving (CBV)` | `Departing (CBV)` | 
|  | `bizTransactionList` | 
|  | `bizTransactionID` | `GDTI` of pallet note | `GDTI` of pallet note | 
|  | `sourceList` |
|  | `source` `type`:`possessing party (CBV)` | `PGLN` of delivering LSP | n./a. |
|  | `source` `type`:`owning party (CBV)` | `PGLN` of sending exchange party | `PGLN` of sending exchange party |
|  | `destinationList` |
|  | `destination` `type`:`possessing party (CBV)` | n./a. | `PGLN` of sending LSP |
|  | `destination` `type`:`owning party (CBV)` | `PGLN` of receiving exchange party | `PGLN` of receiving exchange party |
|  | `destination` `type`:`location (CBV)` | n./a. | `SGLN` of receiving exchange location |
| Other | `b4l:tradability | `true` or `false` |
|  | `b4l:qualityLevel` | `A`, `B`, or `C` | 
 
Legend/explanation 
* owning_party: actual exchange parties (in open pool system systems the actual owner, in closed pool systems the 'lessee')  
* LSP - Logistics Service Provider 
* RTI - Reusable Transport Item
* GDTI - Global Document Type Identifier 
* GRAI - Global Reusable Asset Identifier 
* SGLN - Global Location Number with or without extension 
* PGLN - Global Location Number of Party   
* Note that if there are tradable and non-tradable OR several quality levels in the course of an arriving/departing event, we need to generate several EPCIS events.  
Rationale: these criteria entail different business processes/pallet values. Thus, we have to properly distinguish quantities pertaining to different qualities.

TO BE COMPLETED