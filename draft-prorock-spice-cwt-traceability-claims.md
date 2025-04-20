---
title: "Traceability Claims"
lang: en
category: std
v: 3
docname: draft-prorock-spice-cwt-traceability-claims-latest
stream: IETF
number:
date:
consensus: true
area: "Security"
workgroup: "Secure Patterns for Internet CrEdentials"
keyword:
 - COSE
 - CBOR Object Signing and Encryption
 - CWT
 - CBOR Web Token
 - Claims
venue:
  group: "Secure Patterns for Internet CrEdentials"
  type: "Working Group"
  mail: "spice@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/spice/"
  github: "mprorock/draft-prorock-spice-cwt-traceability-claims"
  latest: "https://mprorock.github.io/draft-prorock-spice-cwt-traceability-claims/draft-prorock-spice-cwt-traceability-claims.html"

author:
 -
    fullname: "Michael Prorock"
    organization: Tradeverifyd
    email: "m.prorock@tradeverifyd.com"
    country: United States

 -
    fullname: Michael B. Jones
    ins: M.B. Jones
    organization: Self-Issued Consulting
    email: michael_b_jones@hotmail.com
    uri: https://self-issued.info/
    country: United States

normative:
  RFC7519:
  RFC8392:
  ISO.3166:
    target: https://www.iso.org/standard/72482.html
    title: "ISO 3166-1:2020: Codes for the representation of names of countries and their subdivisions"
    author:
    - org: ISO
    date: 2020
  ISO.4217:
    target: https://www.iso.org/standard/64758.html
    title: "ISO 4217:2015: Codes for the representation of currencies"
    author:
    - org: ISO
    date: 2015
  ISO.8601:
    target: https://www.iso.org/standard/70907.html
    title: "ISO 8601-1:2019: Date and time — Representations for information interchange"
    author:
    - org: ISO
    date: 2019

informative:
  IANA.CWT:
    target: https://www.iana.org/assignments/cwt/
    title: CBOR Web Token (CWT) Claims
    author:
    - org: IANA

  IANA.JWT:
    target: https://www.iana.org/assignments/jwt/
    title: JSON Web Token Claims
    author:
    - org: IANA

  CATAIR:
    target: https://www.cbp.gov/trade/ace/catair
    title: ACE Automated Broker Interface (ABI) CBP and Trade Automated Interface Requirements (CATAIR)
    author:
    - org: U.S. Customs and Border Protection
    date: April 2025

  TrackTrace:
    target: https://unece.org/sites/default/files/2025-01/BRS-IntegratedTrackandTraceforMulti-ModalTransportationv0.1-Final.pdf
    title: Integrated Track and Trace for Multi-Modal Transportation
    author:
    - org: United Nations Centre for Trade Facilitation and Electronic Business (UN/CEFACT)
    date: September 2022

  TraceabilityVocab:
    target: https://w3c-ccg.github.io/traceability-vocab/
    title: "Traceability Vocabulary v1.0: A vocabulary for traceability in supply chains"
    author:
      -
        ins: N. Jespersen
        name: Nis Jespersen
      -
        ins: M. Alkhraishi
        name: Mahmoud Alkhraishi
      -
        ins: B. Zundel
        name: Brent Zundel
    date: December 2024
---

--- abstract

This document defines claims to support
traceability of physical goods across supply chains,
focusing on items such as bills of lading, transport modes, and container manifests.
These claims standardize the encoding of essential logistics and transport metadata,
facilitating enhanced transparency and accountability in global supply chains.
These claims are registered for use in both CBOR Web Tokens (CWTs)
and JSON Web Tokens (JWTs).

--- middle

# Introduction

This document defines a set of claims intended to enable the
traceability of physical goods across various stages of transportation and storage.
These claims capture critical information necessary for documenting
the movement of goods in supply chains,
thereby supporting regulatory compliance and operational efficiency.
These claims are defined for both CBOR Web Tokens (CWTs) [RFC8392]
and JSON Web Tokens (JWTs) [RFC7519].

These claims are informed by the following documents,
among others:
ACE Automated Broker Interface (ABI) CBP and Trade Automated Interface Requirements (CATAIR) [CATAIR],
Integrated Track and Trace for Multi-Modal Transportation [TrackTrace],
and
Traceability Vocabulary v1.0: A vocabulary for traceability in supply chains [TraceabilityVocab].

# Conventions and Definitions

{::boilerplate bcp14-tagged}


# Security Considerations

These claims are designed to enhance transparency in supply chain tracking but should be handled securely to prevent unauthorized access to sensitive data. Confidentiality and integrity of these claims must be considered, particularly when shared across untrusted or unsecured networks. Use of selective disclosure techniques and careful consideration of data minimization requirements SHOULD be considered when using these claims.


# IANA Considerations

## CBOR Web Token (CWT) Claims

This specification registers the following claims in the
IANA "CBOR Web Token (CWT) Claims" registry [IANA.CWT] established by [RFC8392].

### Goods Identifier {#product_id}

* Claim Name: product_id
* Claim Description: A unique identifier for the physical product(s) or shipment being tracked. May correspond to SKU, product ID, or batch number.
* JWT Claim Name: product_id
* Claim Key: TBD (requested assignment 320)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{product_id}} of this specification

### Shipment ID {#shipment_id}

* Claim Name: shipment_id
* Claim Description: Unique identifier assigned to a specific shipment.
* JWT Claim Name: shipment_id
* Claim Key: TBD (requested assignment 321)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{shipment_id}} of this specification

### Bill of Lading Number {#bill_of_lading_number}

* Claim Name: bill_of_lading_number
* Claim Description: Identifier for the bill of lading associated with the goods.
* JWT Claim Name: bill_of_lading_number
* Claim Key: TBD (requested assignment 322)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{bill_of_lading_number}} of this specification

### Transport Mode {#transport_mode}

* Claim Name: transport_mode
* Claim Description: Mode of transport used for the shipment. (Recommended values: "air", "sea", "rail", "truck")
* JWT Claim Name: transport_mode
* Claim Key: TBD (requested assignment 323)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{transport_mode}} of this specification

### Container ID {#container_id}

* Claim Name: container_id
* Claim Description: Unique identifier for the container used in the shipment.
* JWT Claim Name: container_id
* Claim Key: TBD (requested assignment 324)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{container_id}} of this specification

### Origin Location {#origin_location}

* Claim Name: origin_location
* Claim Description: Geographical origin of the goods, represented as an [ISO.3166] alpha-2 country code string or specific address
* JWT Claim Name: origin_location
* Claim Key: TBD (requested assignment 325)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{origin_location}} of this specification

### Destination Location {#destination_location}

* Claim Name: destination_location
* Claim Description: Final destination of the goods in the shipment.
* JWT Claim Name: destination_location
* Claim Key: TBD (requested assignment 326)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{destination_location}} of this specification

### Carrier ID {#carrier_id}

* Claim Name: carrier_id
* Claim Description: Identifier for the carrier or logistics provider responsible for the shipment.
* JWT Claim Name: carrier_id
* Claim Key: TBD (requested assignment 327)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{carrier_id}} of this specification

### Estimated Delivery Date {#estimated_delivery_date}

* Claim Name: estimated_delivery_date
* Claim Description: Expected delivery date for the shipment, represented as an [ISO.8601] date and time string
* JWT Claim Name: estimated_delivery_date
* Claim Key: TBD (requested assignment 328)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{estimated_delivery_date}} of this specification

### Customs Declaration Number {#customs_declaration_number}

* Claim Name: customs_declaration_number
* Claim Description: Identifier for the customs declaration associated with the shipment.
* JWT Claim Name: customs_declaration_number
* Claim Key: TBD (requested assignment 329)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{customs_declaration_number}} of this specification

### Commodity Description {#commodity_description}

* Claim Name: commodity_description
* Claim Description: Description of the commodity or goods being transported.
* JWT Claim Name: commodity_description
* Claim Key: TBD (requested assignment 330)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{commodity_description}} of this specification

### HS Code {#hs_code}

* Claim Name: hs_code
* Claim Description: Harmonized System (HS) code for the goods.
* JWT Claim Name: hs_code
* Claim Key: TBD (requested assignment 331)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{hs_code}} of this specification

### Gross Weight {#gross_weight}

* Claim Name: gross_weight
* Claim Description: Gross weight of the shipment, in kilograms.
* JWT Claim Name: gross_weight
* Claim Key: TBD (requested assignment 332)
* Claim Value Type: integer
* Change Controller: IETF
* Reference: {{gross_weight}} of this specification

### Temperature Min Requirement {#temperature_requirement_min}

* Claim Name: temperature_requirement_min
* Claim Description: Minimum temperature (in Celsius) required for transport or storage of the goods.
* JWT Claim Name: temperature_requirement_min
* Claim Key: TBD (requested assignment 333)
* Claim Value Type: float
* Change Controller: IETF
* Reference: {{temperature_requirement_min}} of this specification

### Temperature Max Requirement {#temperature_requirement_max}

* Claim Name: temperature_requirement_max
* Claim Description: Maximum temperature (in Celsius) required for transport or storage of the goods.
* JWT Claim Name: temperature_requirement_max
* Claim Key: TBD (requested assignment 334)
* Claim Value Type: float
* Change Controller: IETF
* Reference: {{temperature_requirement_max}} of this specification

### Last Known Location {#last_known_location}

* Claim Name: last_known_location
* Claim Description: Most recent location update for the goods.
* JWT Claim Name: last_known_location
* Claim Key: TBD (requested assignment 335)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{last_known_location}} of this specification

### Tariff Code {#tariff_code}

* Claim Name: tariff_code
* Claim Description: Tariff code applicable to the goods, including national tariff classifications or specific duty codes.
* JWT Claim Name: tariff_code
* Claim Key: TBD (requested assignment 336)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{tariff_code}} of this specification

### Country of Origin {#country_of_origin}

* Claim Name: country_of_origin
* Claim Description: The country where the goods were produced or manufactured, represented as an [ISO.3166] alpha-2 country code string
* JWT Claim Name: country_of_origin
* Claim Key: TBD (requested assignment 337)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{country_of_origin}} of this specification

### Customs Value {#customs_value}

* Claim Name: customs_value
* Claim Description: Declared value of the goods for customs purposes, typically in the transaction currency.
* JWT Claim Name: customs_value
* Claim Key: TBD (requested assignment 338)
* Claim Value Type: float
* Change Controller: IETF
* Reference: {{customs_value}} of this specification

### Currency Code {#currency_code}

* Claim Name: currency_code
* Claim Description: Currency code for the customs value and other monetary amounts, represented as an [ISO.4217] alpha-3 currency code string
* JWT Claim Name: currency_code
* Claim Key: TBD (requested assignment 339)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{currency_code}} of this specification

### Import/Export License Number {#license_number}

* Claim Name: license_number
* Claim Description: License or permit number required for the import or export of the goods.
* JWT Claim Name: license_number
* Claim Key: TBD (requested assignment 340)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{license_number}} of this specification

### Sanctions Reference {#sanctions_reference}

* Claim Name: sanctions_reference
* Claim Description: Reference to applicable sanctions lists or regulations affecting the goods or involved parties.
* JWT Claim Name: sanctions_reference
* Claim Key: TBD (requested assignment 341)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{sanctions_reference}} of this specification

### Legal Jurisdiction {#legal_jurisdiction}

* Claim Name: legal_jurisdiction
* Claim Description: Legal jurisdiction(s) governing the transaction, represented as an [ISO.3166] alpha-2 country code string or specific legal identifiers
* JWT Claim Name: legal_jurisdiction
* Claim Key: TBD (requested assignment 342)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{legal_jurisdiction}} of this specification

### Importer Code {#importer_code}

* Claim Name: importer_code
* Claim Description: Code identifying the importer, such as a VAT number or EORI number.
* JWT Claim Name: importer_code
* Claim Key: TBD (requested assignment 343)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{importer_code}} of this specification

### Exporter Code {#exporter_code}

* Claim Name: exporter_code
* Claim Description: Code identifying the exporter, such as a VAT number or EORI number.
* JWT Claim Name: exporter_code
* Claim Key: TBD (requested assignment 344)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{exporter_code}} of this specification

### International Commercial Terms {#incoterms}

* Claim Name: incoterms
* Claim Description: International commercial terms defining responsibilities between buyer and seller, e.g., "FOB," "CIF."
* JWT Claim Name: incoterms
* Claim Key: TBD (requested assignment 345)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{incoterms}} of this specification

### Regulatory Compliance Codes {#regulatory_compliance_codes}

* Claim Name: regulatory_compliance_codes
* Claim Description: Codes indicating compliance with specific regulations or standards (e.g., safety certifications, environmental standards).
* JWT Claim Name: regulatory_compliance_codes
* Claim Key: TBD (requested assignment 346)
* Claim Value Type: array of text strings
* Change Controller: IETF
* Reference: {{regulatory_compliance_codes}} of this specification

### Additional Documents Required {#additional_documents_required}

* Claim Name: additional_documents_required
* Claim Description: List of additional documents required for customs clearance, such as certificates of origin or inspection reports.
* JWT Claim Name: additional_documents_required
* Claim Key: TBD (requested assignment 347)
* Claim Value Type: array of text strings
* Change Controller: IETF
* Reference: {{additional_documents_required}} of this specification

### Freight Charges {#freight_charges}

* Claim Name: freight_charges
* Claim Description: Transportation costs associated with the shipment, used for customs valuation.
* JWT Claim Name: freight_charges
* Claim Key: TBD (requested assignment 348)
* Claim Value Type: float
* Change Controller: IETF
* Reference: {{freight_charges}} of this specification

### Insurance Charges {#insurance_charges}

* Claim Name: insurance_charges
* Claim Description: Insurance costs for the shipment, used in determining customs value.
* JWT Claim Name: insurance_charges
* Claim Key: TBD (requested assignment 349)
* Claim Value Type: float
* Change Controller: IETF
* Reference: {{insurance_charges}} of this specification

### Packing Costs {#packing_costs}

* Claim Name: packing_costs
* Claim Description: Costs associated with packing the goods, relevant for customs valuation.
* JWT Claim Name: packing_costs
* Claim Key: TBD (requested assignment 350)
* Claim Value Type: float
* Change Controller: IETF
* Reference: {{packing_costs}} of this specification

### Place of Loading {#place_of_loading}

* Claim Name: place_of_loading
* Claim Description: Location where the goods were loaded for shipment, often a port or warehouse.
* JWT Claim Name: place_of_loading
* Claim Key: TBD (requested assignment 351)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{place_of_loading}} of this specification

### Place of Discharge {#place_of_discharge}

* Claim Name: place_of_discharge
* Claim Description: Location where the goods are scheduled to be unloaded.
* JWT Claim Name: place_of_discharge
* Claim Key: TBD (requested assignment 352)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{place_of_discharge}} of this specification

### Consignee Information {#consignee_information}

* Claim Name: consignee_information
* Claim Description: Information about the consignee, including name, address, and contact details.
* JWT Claim Name: consignee_information
* Claim Key: TBD (requested assignment 353)
* Claim Value Type: map
* Change Controller: IETF
* Reference: {{consignee_information}} of this specification

### Consignor Information {#consignor_information}

* Claim Name: consignor_information
* Claim Description: Information about the consignor, including name, address, and contact details.
* JWT Claim Name: consignor_information
* Claim Key: TBD (requested assignment 354)
* Claim Value Type: map
* Change Controller: IETF
* Reference: {{consignor_information}} of this specification

### Customs Declaration Date {#customs_declaration_date}

* Claim Name: customs_declaration_date
* Claim Description: Date when the customs declaration was made, represented as an [ISO.8601] date and time string
* JWT Claim Name: customs_declaration_date
* Claim Key: TBD (requested assignment 355)
* Claim Value Type: text string
* Change Controller: IETF
* Reference: {{customs_declaration_date}} of this specification

## JSON Web Token (JWT) Claims

This specification registers the following claims in the
IANA "JSON Web Token Claims" registry [IANA.JWT] established by [RFC7519].

### Goods Identifier

* Claim Name: product_id
* Claim Description: A unique identifier for the physical product(s) or shipment being tracked. May correspond to SKU, product ID, or batch number.
* Change Controller: IETF
* Reference: {{product_id}} of this specification

### Shipment ID

* Claim Name: shipment_id
* Claim Description: Unique identifier assigned to a specific shipment.
* Change Controller: IETF
* Reference: {{shipment_id}} of this specification

### Bill of Lading Number

* Claim Name: bill_of_lading_number
* Claim Description: Identifier for the bill of lading associated with the goods.
* Change Controller: IETF
* Reference: {{bill_of_lading_number}} of this specification

### Transport Mode

* Claim Name: transport_mode
* Claim Description: Mode of transport used for the shipment. (Recommended values: "air", "sea", "rail", "truck")
* Change Controller: IETF
* Reference: {{transport_mode}} of this specification

### Container ID

* Claim Name: container_id
* Claim Description: Unique identifier for the container used in the shipment.
* Change Controller: IETF
* Reference: {{container_id}} of this specification

### Origin Location

* Claim Name: origin_location
* Claim Description: Geographical origin of the goods, represented as an [ISO.3166] alpha-2 country code string or specific address
* Change Controller: IETF
* Reference: {{origin_location}} of this specification

### Destination Location

* Claim Name: destination_location
* Claim Description: Final destination of the goods in the shipment.
* Change Controller: IETF
* Reference: {{destination_location}} of this specification

### Carrier ID

* Claim Name: carrier_id
* Claim Description: Identifier for the carrier or logistics provider responsible for the shipment.
* Change Controller: IETF
* Reference: {{carrier_id}} of this specification

### Estimated Delivery Date

* Claim Name: estimated_delivery_date
* Claim Description: Expected delivery date for the shipment, represented as an [ISO.8601] date and time string
* Change Controller: IETF
* Reference: {{estimated_delivery_date}} of this specification

### Customs Declaration Number

* Claim Name: customs_declaration_number
* Claim Description: Identifier for the customs declaration associated with the shipment.
* Change Controller: IETF
* Reference: {{customs_declaration_number}} of this specification

### Commodity Description

* Claim Name: commodity_description
* Claim Description: Description of the commodity or goods being transported.
* Change Controller: IETF
* Reference: {{commodity_description}} of this specification

### HS Code

* Claim Name: hs_code
* Claim Description: Harmonized System (HS) code for the goods.
* Change Controller: IETF
* Reference: {{hs_code}} of this specification

### Gross Weight

* Claim Name: gross_weight
* Claim Description: Gross weight of the shipment, in kilograms.
* Change Controller: IETF
* Reference: {{gross_weight}} of this specification

### Temperature Min Requirement

* Claim Name: temperature_requirement_min
* Claim Description: Minimum temperature (in Celsius) required for transport or storage of the goods.
* Change Controller: IETF
* Reference: {{temperature_requirement_min}} of this specification

### Temperature Max Requirement

* Claim Name: temperature_requirement_max
* Claim Description: Maximum temperature (in Celsius) required for transport or storage of the goods.
* Change Controller: IETF
* Reference: {{temperature_requirement_max}} of this specification

### Last Known Location

* Claim Name: last_known_location
* Claim Description: Most recent location update for the goods.
* Change Controller: IETF
* Reference: {{last_known_location}} of this specification

### Tariff Code

* Claim Name: tariff_code
* Claim Description: Tariff code applicable to the goods, including national tariff classifications or specific duty codes.
* Change Controller: IETF
* Reference: {{tariff_code}} of this specification

### Country of Origin

* Claim Name: country_of_origin
* Claim Description: The country where the goods were produced or manufactured, represented as an [ISO.3166] alpha-2 country code string
* Change Controller: IETF
* Reference: {{country_of_origin}} of this specification

### Customs Value

* Claim Name: customs_value
* Claim Description: Declared value of the goods for customs purposes, typically in the transaction currency.
* Change Controller: IETF
* Reference: {{customs_value}} of this specification

### Currency Code

* Claim Name: currency_code
* Claim Description: Currency code for the customs value and other monetary amounts, represented as an [ISO.4217] alpha-3 currency code string
* Change Controller: IETF
* Reference: {{currency_code}} of this specification

### Import/Export License Number

* Claim Name: license_number
* Claim Description: License or permit number required for the import or export of the goods.
* Change Controller: IETF
* Reference: {{license_number}} of this specification

### Sanctions Reference

* Claim Name: sanctions_reference
* Claim Description: Reference to applicable sanctions lists or regulations affecting the goods or involved parties.
* Change Controller: IETF
* Reference: {{sanctions_reference}} of this specification

### Legal Jurisdiction

* Claim Name: legal_jurisdiction
* Claim Description: Legal jurisdiction(s) governing the transaction, represented as an [ISO.3166] alpha-2 country code string or specific legal identifiers
* Change Controller: IETF
* Reference: {{legal_jurisdiction}} of this specification

### Importer Code

* Claim Name: importer_code
* Claim Description: Code identifying the importer, such as a VAT number or EORI number.
* Change Controller: IETF
* Reference: {{importer_code}} of this specification

### Exporter Code

* Claim Name: exporter_code
* Claim Description: Code identifying the exporter, such as a VAT number or EORI number.
* Change Controller: IETF
* Reference: {{exporter_code}} of this specification

### International Commercial Terms

* Claim Name: incoterms
* Claim Description: International commercial terms defining responsibilities between buyer and seller, e.g., "FOB," "CIF."
* Change Controller: IETF
* Reference: {{incoterms}} of this specification

### Regulatory Compliance Codes

* Claim Name: regulatory_compliance_codes
* Claim Description: Codes indicating compliance with specific regulations or standards (e.g., safety certifications, environmental standards).
* Change Controller: IETF
* Reference: {{regulatory_compliance_codes}} of this specification

### Additional Documents Required

* Claim Name: additional_documents_required
* Claim Description: List of additional documents required for customs clearance, such as certificates of origin or inspection reports.
* Change Controller: IETF
* Reference: {{additional_documents_required}} of this specification

### Freight Charges

* Claim Name: freight_charges
* Claim Description: Transportation costs associated with the shipment, used for customs valuation.
* Change Controller: IETF
* Reference: {{freight_charges}} of this specification

### Insurance Charges

* Claim Name: insurance_charges
* Claim Description: Insurance costs for the shipment, used in determining customs value.
* Change Controller: IETF
* Reference: {{insurance_charges}} of this specification

### Packing Costs

* Claim Name: packing_costs
* Claim Description: Costs associated with packing the goods, relevant for customs valuation.
* Change Controller: IETF
* Reference: {{packing_costs}} of this specification

### Place of Loading

* Claim Name: place_of_loading
* Claim Description: Location where the goods were loaded for shipment, often a port or warehouse.
* Change Controller: IETF
* Reference: {{place_of_loading}} of this specification

### Place of Discharge

* Claim Name: place_of_discharge
* Claim Description: Location where the goods are scheduled to be unloaded.
* Change Controller: IETF
* Reference: {{place_of_discharge}} of this specification

### Consignee Information

* Claim Name: consignee_information
* Claim Description: Information about the consignee, including name, address, and contact details.
* Change Controller: IETF
* Reference: {{consignee_information}} of this specification

### Consignor Information

* Claim Name: consignor_information
* Claim Description: Information about the consignor, including name, address, and contact details.
* Change Controller: IETF
* Reference: {{consignor_information}} of this specification

### Customs Declaration Date

* Claim Name: customs_declaration_date
* Claim Description: Date when the customs declaration was made, represented as an [ISO.8601] date and time string
* Change Controller: IETF
* Reference: {{customs_declaration_date}} of this specification

--- back

# Acknowledgments
{:numbered="false"}

A.J. Stein
contributed to this specification.

# Document History
{: numbered="false"}

-01

* Added registrations of JWT claims corresponding to the CWT claims.
* Updated CWT Claims registrations to supply all fields in the registration template.
* Fixed IANA Considerations header, as suggested by A.J. Stein.
* Added references for ISO specs.
* Specified the use of [ISO.3166] alpha-2 country code strings and [ISO.4217] alpha-3 currency code strings.
* Added references to sources of traceability claims.
* Added Michael B. Jones as an author.

-00

* Initial individual draft
