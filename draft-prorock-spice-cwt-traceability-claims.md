---
title: "SPICE Traceability CWT Claims"
category: info
v: 3
docname: draft-prorock-spice-cwt-traceability-claims-latest
stream: IETF
number:
date:
consensus: true
area: ""
workgroup: "Secure Patterns for Internet CrEdentials"
keyword:
 - cose
 - cwt
venue:
  group: "Secure Patterns for Internet CrEdentials"
  type: ""
  mail: "spice@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/spice/"
  github: "mprorock/draft-prorock-spice-cwt-traceability-claims"
  latest: "https://mprorock.github.io/draft-prorock-spice-cwt-traceability-claims/draft-prorock-spice-cwt-traceability-claims.html"

author:
 -
    fullname: "Michael Prorock"
    organization: mesur.io
    email: "mprorock@mesur.io"

normative:
  RFC8392:
  BCP205:

informative:
---

--- abstract

This document proposes additional claims for CBOR Web Tokens (CWT) to support traceability of physical goods across supply chains, focusing on items such as bills of lading, transport modes, and container manifests. These claims aim to standardize the encoding of essential logistics and transport metadata, facilitating enhanced transparency and accountability in global supply chains.


--- middle

# Introduction

This document defines a set of claims for CBOR Web Tokens (CWT) intended to enable the traceability of physical goods across various stages of transportation and storage. These claims capture critical information necessary for documenting the movement of goods in supply chains, thereby supporting regulatory compliance and operational efficiency.


# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations

These claims are designed to enhance transparency in supply chain tracking but should be handled securely to prevent unauthorized access to sensitive data. Confidentiality and integrity of these claims must be considered, particularly when shared across untrusted or unsecured networks. Use of selective disclosure techniques and careful consideration of data minimization requirements SHOULD be considered when using these claims.


# IANA Considerations

## CBOR Web Token (CWT) Claims

IANA is requested to add the following entries to the CWT claims registry (https://www.iana.org/assignments/cwt/cwt.xhtml).


### Goods Identifier

The following completed registration template per RFC8392 is provided:

Name: product_id
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: A unique identifier for the physical product(s) or shipment being tracked. May correspond to SKU, product ID, or batch number.
Reference: RFC XXXX

### Shipment ID

The following completed registration template per RFC8392 is provided:

Name: shipment_id
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Unique identifier assigned to a specific shipment.
Reference: RFC XXXX

### Bill of Lading Number

The following completed registration template per RFC8392 is provided:

Name: bill_of_lading_number
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Identifier for the bill of lading associated with the goods.
Reference: RFC XXXX

### Transport Mode

The following completed registration template per RFC8392 is provided:

Name: transport_mode
Label: TBD
Value Type: text string (recommended values: “air,” “sea,” “rail,” “truck”)
Value Registry: (empty)
Description: Mode of transport used for the shipment.
Reference: RFC XXXX

### Container ID

The following completed registration template per RFC8392 is provided:

Name: container_id
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Unique identifier for the container used in the shipment.
Reference: RFC XXXX

### Origin Location

The following completed registration template per RFC8392 is provided:

Name: origin_location
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Geographical origin of the goods, represented as a location code (e.g., ISO country code) or specific address.
Reference: RFC XXXX

### Destination Location

The following completed registration template per RFC8392 is provided:

Name: destination_location
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Final destination of the goods in the shipment.
Reference: RFC XXXX

### Carrier ID

The following completed registration template per RFC8392 is provided:

Name: carrier_id
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Identifier for the carrier or logistics provider responsible for the shipment.
Reference: RFC XXXX

### Estimated Delivery Date

The following completed registration template per RFC8392 is provided:

Name: estimated_delivery_date
Label: TBD
Value Type: text string (ISO8601 format)
Value Registry: (empty)
Description: Expected delivery date for the shipment.
Reference: RFC XXXX

### Customs Declaration Number

The following completed registration template per RFC8392 is provided:

Name: customs_declaration_number
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Identifier for the customs declaration associated with the shipment.
Reference: RFC XXXX

### Commodity Description

The following completed registration template per RFC8392 is provided:

Name: commodity_description
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Description of the commodity or goods being transported.
Reference: RFC XXXX

### HS Code

The following completed registration template per RFC8392 is provided:

Name: hs_code
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Harmonized System (HS) code for the goods.
Reference: RFC XXXX

### Gross Weight

The following completed registration template per RFC8392 is provided:

Name: gross_weight
Label: TBD
Value Type: integer
Value Registry: (empty)
Description: Gross weight of the shipment, in kilograms.
Reference: RFC XXXX

### Temperature Min Requirement

The following completed registration template per RFC8392 is provided:

Name: temperature_requirement_min
Label: TBD
Value Type: float
Value Registry: (empty)
Description: Minimum temperature (in Celsius) required for transport or storage of the goods.
Reference: RFC XXXX

### Temperature Max Requirement

The following completed registration template per RFC8392 is provided:

Name: temperature_requirement_max
Label: TBD
Value Type: float
Value Registry: (empty)
Description: Maximum temperature (in Celsius) required for transport or storage of the goods.
Reference: RFC XXXX

### Last Known Location

The following completed registration template per RFC8392 is provided:

Name: last_known_location
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Most recent location update for the goods.
Reference: RFC XXXX

### Tariff Code

The following completed registration template per RFC8392 is provided:

Name: tariff_code
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Tariff code applicable to the goods, including national tariff classifications or specific duty codes.
Reference: RFC XXXX

### Country of Origin

The following completed registration template per RFC8392 is provided:

Name: country_of_origin
Label: TBD
Value Type: text string (ISO 3166-1 alpha-2 country code)
Value Registry: (empty)
Description: The country where the goods were produced or manufactured.
Reference: RFC XXXX

### Customs Value

The following completed registration template per RFC8392 is provided:

Name: customs_value
Label: TBD
Value Type: float
Value Registry: (empty)
Description: Declared value of the goods for customs purposes, typically in the transaction currency.
Reference: RFC XXXX

### Currency Code

The following completed registration template per RFC8392 is provided:

Name: currency_code
Label: TBD
Value Type: text string (ISO 4217 currency code)
Value Registry: (empty)
Description: Currency code for the customs value and other monetary amounts, as per ISO 4217.
Reference: RFC XXXX

### Import/Export License Number

The following completed registration template per RFC8392 is provided:

Name: license_number
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: License or permit number required for the import or export of the goods.
Reference: RFC XXXX

### Sanctions Reference

The following completed registration template per RFC8392 is provided:

Name: sanctions_reference
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Reference to applicable sanctions lists or regulations affecting the goods or involved parties.
Reference: RFC XXXX

### Legal Jurisdiction

The following completed registration template per RFC8392 is provided:

Name: legal_jurisdiction
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Legal jurisdiction(s) governing the transaction, represented as country codes or specific legal identifiers.
Reference: RFC XXXX

### Importer Code

The following completed registration template per RFC8392 is provided:

Name: importer_code
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Code identifying the importer, such as a VAT number or EORI number.
Reference: RFC XXXX

### Exporter Code

The following completed registration template per RFC8392 is provided:

Name: exporter_code
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Code identifying the exporter, such as a VAT number or EORI number.
Reference: RFC XXXX

### Incoterms

The following completed registration template per RFC8392 is provided:

Name: incoterms
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: International commercial terms defining responsibilities between buyer and seller, e.g., "FOB," "CIF."
Reference: RFC XXXX

### Regulatory Compliance Codes

The following completed registration template per RFC8392 is provided:

Name: regulatory_compliance_codes
Label: TBD
Value Type: array of text strings
Value Registry: (empty)
Description: Codes indicating compliance with specific regulations or standards (e.g., safety certifications, environmental standards).
Reference: RFC XXXX

### Additional Documents Required

The following completed registration template per RFC8392 is provided:

Name: additional_documents_required
Label: TBD
Value Type: array of text strings
Value Registry: (empty)
Description: List of additional documents required for customs clearance, such as certificates of origin or inspection reports.
Reference: RFC XXXX

### Freight Charges

The following completed registration template per RFC8392 is provided:

Name: freight_charges
Label: TBD
Value Type: float
Value Registry: (empty)
Description: Transportation costs associated with the shipment, used for customs valuation.
Reference: RFC XXXX

### Insurance Charges

The following completed registration template per RFC8392 is provided:

Name: insurance_charges
Label: TBD
Value Type: float
Value Registry: (empty)
Description: Insurance costs for the shipment, used in determining customs value.
Reference: RFC XXXX

### Packing Costs

The following completed registration template per RFC8392 is provided:

Name: packing_costs
Label: TBD
Value Type: float
Value Registry: (empty)
Description: Costs associated with packing the goods, relevant for customs valuation.
Reference: RFC XXXX

### Place of Loading

The following completed registration template per RFC8392 is provided:

Name: place_of_loading
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Location where the goods were loaded for shipment, often a port or warehouse.
Reference: RFC XXXX

### Place of Discharge

The following completed registration template per RFC8392 is provided:

Name: place_of_discharge
Label: TBD
Value Type: text string
Value Registry: (empty)
Description: Location where the goods are scheduled to be unloaded.
Reference: RFC XXXX

### Consignee Information

The following completed registration template per RFC8392 is provided:

Name: consignee_information
Label: TBD
Value Type: map
Value Registry: (empty)
Description: Information about the consignee, including name, address, and contact details.
Reference: RFC XXXX

### Consignor Information

The following completed registration template per RFC8392 is provided:

Name: consignor_information
Label: TBD
Value Type: map
Value Registry: (empty)
Description: Information about the consignor, including name, address, and contact details.
Reference: RFC XXXX

### Customs Declaration Date

The following completed registration template per RFC8392 is provided:

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
