title: "SPICE Traceability CWT Claims"
abbrev: "stcc"
category: info
v: 3
docname: draft-prorock-spice-cwt-traceability-claims
stream: IETF
number:
date:
consensus: true
area: "Security"
workgroup: "Secure Patterns for Internet CrEdentials"
keyword:
 - cose
 - cwt
<!-- venue:
  group: WG
  type: Working Group
  mail: WG@example.com
  arch: https://example.com/WG
  github: USER/REPO
  latest: https://example.com/LATEST -->

author:
 -
    fullname: "Michael Prorock"
    organization: mesur.io
    email: "mprorock@mesur.io"

normative:
  RFC8392:
  BCP205:

informative:


--- abstract

This document proposes additional claims for CBOR Web Tokens (CWT) to support traceability of physical goods across supply chains, focusing on items such as bills of lading, transport modes, and container manifests. These claims aim to standardize the encoding of essential logistics and transport metadata, facilitating enhanced transparency and accountability in global supply chains.


--- middle

# Introduction

This document defines a set of claims for CBOR Web Tokens (CWT) intended to enable the traceability of physical goods across various stages of transportation and storage. These claims capture critical information necessary for documenting the movement of goods in supply chains, thereby supporting regulatory compliance and operational efficiency.


# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations

These claims are designed to enhance transparency in supply chain tracking but should be handled securely to prevent unauthorized access to sensitive data. Confidentiality and integrity of these claims must be considered, particularly when shared across untrusted or unsecured networks. Use of selective disclosure techniques and careful consideration of data minimization requirements SHOULD be considered when using these claims.


## 4. IANA Considerations

## CWT Claims

IANA is requested to add the following entries to the CWT claims registry (https://www.iana.org/assignments/cose/cose.xhtml#header-parameters).


### Goods Identifier
Name: product_id
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: A unique identifier for the physical product(s) or shipment being tracked. May correspond to SKU, product ID, or batch number.
Reference: RFC XXXX

### Shipment ID
Name: shipment_id
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Unique identifier assigned to a specific shipment.
Reference: RFC XXXX

### Bill of Lading Number
Name: bill_of_lading_number
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Identifier for the bill of lading associated with the goods.
Reference: RFC XXXX

### Transport Mode
Name: transport_mode
Label: TBD
Value Type: text string (recommended values: “air,” “sea,” “rail,” “truck”)
Value Registry: (empty)
Description: Mode of transport used for the shipment.
Reference: RFC XXXX

### Container ID
Name: container_id
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Unique identifier for the container used in the shipment.
Reference: RFC XXXX

### Origin Location
Name: origin_location
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Geographical origin of the goods, represented as a location code (e.g., ISO country code) or specific address.
Reference: RFC XXXX

### Destination Location
Name: destination_location
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Final destination of the goods in the shipment.
Reference: RFC XXXX

### Carrier ID
Name: carrier_id
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Identifier for the carrier or logistics provider responsible for the shipment.
Reference: RFC XXXX

### Estimated Delivery Date
Name: estimated_delivery_date
Label: TBD
Value Type: text string (ISO8601 format)
Value Registry: (empty)
Description: Expected delivery date for the shipment.
Reference: RFC XXXX

### Customs Declaration Number
Name: customs_declaration_number
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Identifier for the customs declaration associated with the shipment.
Reference: RFC XXXX

### Commodity Description
Name: commodity_description
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Description of the commodity or goods being transported.
Reference: RFC XXXX

### HS Code
Name: hs_code
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Harmonized System (HS) code for the goods.
Reference: RFC XXXX

### Gross Weight
Name: gross_weight
Label: TBD
Value Type: integer
Value Registry: (empty)
Description: Gross weight of the shipment, in kilograms.
Reference: RFC XXXX

### Temperature Min Requirement
Name: temperature_requirement_min
Label: TBD
Value Type: float
Value Registry: (empty)
Description: Minimum temperature (in Celsius) required for transport or storage of the goods.
Reference: RFC XXXX

### Temperature Max Requirement
Name: temperature_requirement_max
Label: TBD
Value Type: float
Value Registry: (empty)
Description: Maximum temperature (in Celsius) required for transport or storage of the goods.
Reference: RFC XXXX

### Last Known Location
Name: last_known_location
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Most recent location update for the goods.
Reference: RFC XXXX

### Tariff Code
Name: tariff_code  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: Tariff code applicable to the goods, including national tariff classifications or specific duty codes.  
Reference: RFC XXXX  

### Country of Origin
Name: country_of_origin  
Label: TBD  
Value Type: text string (ISO 3166-1 alpha-2 country code)  
Value Registry: (empty)  
Description: The country where the goods were produced or manufactured.  
Reference: RFC XXXX  

### Customs Value
Name: customs_value  
Label: TBD  
Value Type: float  
Value Registry: (empty)  
Description: Declared value of the goods for customs purposes, typically in the transaction currency.  
Reference: RFC XXXX  

### Currency Code
Name: currency_code  
Label: TBD  
Value Type: text string (ISO 4217 currency code)  
Value Registry: (empty)  
Description: Currency code for the customs value and other monetary amounts, as per ISO 4217.  
Reference: RFC XXXX  

### Import/Export License Number
Name: license_number  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: License or permit number required for the import or export of the goods.  
Reference: RFC XXXX  

### Sanctions Reference
Name: sanctions_reference  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: Reference to applicable sanctions lists or regulations affecting the goods or involved parties.  
Reference: RFC XXXX  

### Legal Jurisdiction
Name: legal_jurisdiction  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: Legal jurisdiction(s) governing the transaction, represented as country codes or specific legal identifiers.  
Reference: RFC XXXX  

### Importer Code
Name: importer_code  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: Code identifying the importer, such as a VAT number or EORI number.  
Reference: RFC XXXX  

### Exporter Code
Name: exporter_code  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: Code identifying the exporter, such as a VAT number or EORI number.  
Reference: RFC XXXX  

### Incoterms
Name: incoterms  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: International commercial terms defining responsibilities between buyer and seller, e.g., "FOB," "CIF."  
Reference: RFC XXXX  

### Regulatory Compliance Codes
Name: regulatory_compliance_codes  
Label: TBD  
Value Type: array of text strings  
Value Registry: (empty)  
Description: Codes indicating compliance with specific regulations or standards (e.g., safety certifications, environmental standards).  
Reference: RFC XXXX  

### Additional Documents Required
Name: additional_documents_required  
Label: TBD  
Value Type: array of text strings  
Value Registry: (empty)  
Description: List of additional documents required for customs clearance, such as certificates of origin or inspection reports.  
Reference: RFC XXXX  

### Freight Charges
Name: freight_charges  
Label: TBD  
Value Type: float  
Value Registry: (empty)  
Description: Transportation costs associated with the shipment, used for customs valuation.  
Reference: RFC XXXX  

### Insurance Charges
Name: insurance_charges  
Label: TBD  
Value Type: float  
Value Registry: (empty)  
Description: Insurance costs for the shipment, used in determining customs value.  
Reference: RFC XXXX  

### Packing Costs
Name: packing_costs  
Label: TBD  
Value Type: float  
Value Registry: (empty)  
Description: Costs associated with packing the goods, relevant for customs valuation.  
Reference: RFC XXXX  

### Place of Loading
Name: place_of_loading  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: Location where the goods were loaded for shipment, often a port or warehouse.  
Reference: RFC XXXX  

### Place of Discharge
Name: place_of_discharge  
Label: TBD  
Value Type: text string  
Value Registry: (empty)  
Description: Location where the goods are scheduled to be unloaded.  
Reference: RFC XXXX  

### Consignee Information
Name: consignee_information  
Label: TBD  
Value Type: map  
Value Registry: (empty)  
Description: Information about the consignee, including name, address, and contact details.  
Reference: RFC XXXX  

### Consignor Information
Name: consignor_information  
Label: TBD  
Value Type: map  
Value Registry: (empty)  
Description: Information about the consignor, including name, address, and contact details.  
Reference: RFC XXXX  

### Customs Declaration Date
Name: customs_declaration_date  
Label: TBD  
Value Type: text string (ISO8601 date format)  
Value Registry: (empty)  
Description: Date when the customs declaration was made.  
Reference: RFC XXXX  

--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.