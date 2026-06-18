# Metadata Schema for IKEA Furniture in Single-Person Households
An XML metadata schema for organizing and describing IKEA furniture products with a focus on space efficiency and multifunctionality for single-person households.

## A. Opening Narrative

### The History of Metadata in the Domain Space

Traditionally, furniture and home goods metadata has been heavily focused on logistics, inventory management, and general retail.

While general e-commerce metadata standards exist to facilitate transactions, they often lack the contextual depth required to evaluate a product's suitability for specific living environments.

With single-person households becoming an increasingly dominant demographic globally due to rapid urbanization, there is a growing need for metadata that goes beyond basic physical attributes to describe how a piece of furniture interacts with limited spaces.

Archival and bibliographic schemas demonstrate clear rules for consistent description across diverse items, which is essential for building a robust product catalog.

## B. Relevant Metadata Standards

To ensure descriptive consistency and semantic richness, this custom schema integrates and draws inspiration from several established metadata standards.

### 1. Dublin Core (DC)

**Elements Used:** `dc:title`, `dc:identifier`, `dc:description`

**Justification:** Dublin Core is highly useful for representing general, foundational metadata such as title, format, description, and identifier. It provides clear, established rules for consistent description across diverse items, ensuring the core descriptive data remains globally interoperable and easy to map across different systems.

### 2. Schema.org & GoodRelations (GR)

**Elements Inspired:** `ik:category` (inspired by GoodRelations), `ik:material`, `ik:colour`, `ik:dimensions`, `ik:price`, `ik:weight`, `ik:url`, `ik:relatedItems` (inspired by Schema.org)

**Justification:** These schemas are particularly relevant for the e-commerce domain, offering well-defined vocabularies for product descriptions. They provide the necessary property models to accurately record commercial data such as price, material, and dimensions, which are essential for furniture catalogs.

### 3. SKOS (Simple Knowledge Organization System)

**Elements Inspired:** `ik:style` (`skos:Concept`)

**Justification:** While SKOS is not originally designed for commercial product catalogs, it offers a highly valuable framework for organizing hierarchical and conceptual relationships between terms. It supports the structural organization of categories and controlled vocabularies. Utilizing structures such as `skos:Concept` is highly effective for building a controlled, machine-enforceable vocabulary for furniture types and design styles.

## C. Vocabulary Specification

### Element Overview Table

| Element Name       | Definition (Brief)                                               | Source                                    |
| ------------------ | ---------------------------------------------------------------- | ----------------------------------------- |
| dc:title           | A name given to the resource.                                    | -                                         |
| dc:identifier      | An unambiguous reference to the resource within a given context. | -                                         |
| dc:description     | An account of the resource.                                      | -                                         |
| ik:category        | Type of furniture (e.g. Bookcase, Bed).                          | gr:category                               |
| ik:style           | Design style (e.g. Minimalist, Modern).                          | skos:Concept                              |
| ik:material        | Primary materials (e.g. Wood, Metal).                            | schema:material                           |
| ik:colour          | The colour of the product.                                       | schema:color                              |
| ik:dimensions      | Product dimensions (Width × Depth × Height).                     | schema:width, schema:depth, schema:height |
| ik:price           | Retail price.                                                    | Custom                                    |
| ik:assembly        | Assembly difficulty and requirements.                            | Custom                                    |
| ik:multifunctionality   | Versatility and multi-functionality.                             | Custom                                    |
| ik:spaceEfficiency | Suitability for small spaces.                                    | Custom                                    |
| ik:weight          | Product weight.                                                  | schema:weight                             |
| ik:relatedItems    | Related products suitable for use with an object.                | schema:isRelatedTo                        |
| ik:url             | URL of the item.                                                 | schema:url                                |

## Full Data Dictionary

### dc:title

| Field           | Value                                        |
| --------------- | -------------------------------------------- |
| Element Name    | dc:title                                     |
| Label           | Product Title                                |
| URI             | https://nhk.singlepersonhousehold/ikea/title |
| Full Definition | A name given to the resource.                |
| Data Values     | String (Text)                                |
| Cardinality     | Mandatory, Non-repeatable                    |
| Comments        | Follows IKEA catalog capitalization.         |
| Example         | LACK side table                              |

### dc:identifier

| Field           | Value                                                            |
| --------------- | ---------------------------------------------------------------- |
| Element Name    | dc:identifier                                                    |
| Label           | Product ID                                                       |
| URI             | https://nhk.singlepersonhousehold/ikea/id                        |
| Full Definition | An unambiguous reference to the resource within a given context. |
| Data Values     | Alphanumeric String (Format: 000.000.00(Country Name))           |
| Cardinality     | Mandatory, Non-repeatable                                        |
| Comments        | Follow the official IKEA 8-digit article number format.          |
| Example         | 005.220.47(South Korea)                                          |

### dc:description

| Field           | Value                                                                       |
| --------------- | --------------------------------------------------------------------------- |
| Element Name    | dc:description                                                              |
| Label           | Description                                                                 |
| URI             | https://nhk.singlepersonhousehold/ikea/description                          |
| Full Definition | An account of the resource.                                                 |
| Data Values     | String (Paragraph)                                                          |
| Cardinality     | Mandatory, Non-repeatable                                                   |
| Comments        | Includes useful notes for single-person households.                         |
| Example         | easy to assemble, lift and move around / enough storage for a limited space |

### ik:category

| Field           | Value                                                          |
| --------------- | -------------------------------------------------------------- |
| Element Name    | ik:category                                                    |
| Label           | Category                                                       |
| URI             | https://nhk.singlepersonhousehold/ikea/category                |
| Full Definition | Type of furniture (e.g. Bookcase, Bed)                         |
| Data Values     | Controlled Vocabulary                                          |
| Cardinality     | Mandatory, Non-repeatable                                      |
| Comments        | Categorized according to IKEA Korea's official classification. |
| Example         | Beds and mattresses                                            |

### ik:style

| Field           | Value                                              |
| --------------- | -------------------------------------------------- |
| Element Name    | ik:style                                           |
| Label           | Design Style                                       |
| URI             | https://nhk.singlepersonhousehold/ikea/designstyle |
| Full Definition | Design style (e.g. Minimalist, Modern)             |
| Data Values     | Controlled Vocabulary                              |
| Cardinality     | Mandatory, Repeatable                              |
| Comments        | These are attributes for interior consistency.     |
| Example         | Minimalist, Modern                                 |

### ik:material

| Field           | Value                                           |
| --------------- | ----------------------------------------------- |
| Element Name    | ik:material                                     |
| Label           | Primary Materials                               |
| URI             | https://nhk.singlepersonhousehold/ikea/material |
| Full Definition | Primary materials (e.g. Wood, Metal)            |
| Data Values     | String                                          |
| Cardinality     | Mandatory, Repeatable                           |
| Comments        | Followed materials according to IKEA’s website. |
| Example         | Wood, Metal                                     |

### ik:colour

| Field           | Value                                             |
| --------------- | ------------------------------------------------- |
| Element Name    | ik:colour                                         |
| Label           | Colour of the item                                |
| URI             | https://nhk.singlepersonhousehold/ikea/colour     |
| Full Definition | Primary product colour (e.g. White, Black, etc)   |
| Data Values     | String                                            |
| Cardinality     | Mandatory,Non-repeatable                             |
| Comments        | This uses colours from the official IKEA website. |
| Example         | White, Black                                      |

### ik:dimensions

| Field           | Value                                             |
| --------------- | ------------------------------------------------- |
| Element Name    | ik:dimensions                                     |
| Label           | Dimensions                                        |
| URI             | https://nhk.singlepersonhousehold/ikea/dimensions |
| Full Definition | Product dimensions (Width, Depth, Height, etc.)   |
| Data Values     | String(Numeric + Unit)                            |
| Cardinality     | Mandatory, Non-Repeatable                         |
| Comments        | ‘width x depth x height’ format is recommended. Depending on the product's shape, the vertical dimension can be labeled as either Length or Depth; if only one of these two values is available, record that specific value.                      |
| Example         | 80x48x100 cm                                      |

### ik:price

| Field           | Value                                             |
| --------------- | ------------------------------------------------- |
| Element Name    | ik:price                                          |
| Label           | Price                                             |
| URI             | https://nhk.singlepersonhousehold/ikea/price      |
| Full Definition | Retail price                                      |
| Data Values     | Numeric (Retail price in local currency)          |
| Cardinality     | Mandatory, Non-repeatable                         |
| Comments        | Refer to IKEA website.                            |
| Example         | ₩65000                                            |

### ik:assembly

| Field           | Value                                             |
| --------------- | ------------------------------------------------- |
| Element Name    | ik:assembly                                       |
| Label           | Assembly Difficulty                               |
| URI             | https://nhk.singlepersonhousehold/ikea/assembly   |
| Full Definition | Assembly difficulty and requirements              |
| Data Values     | Controlled Vocabulary                             |
| Cardinality     | Mandatory, Non-repeatable                         |
| Comments        | Information on whether assembly tools are included can be added as a supplementary note.                                                   |
| Example         | FullyAssembled                                    |

### ik:multifunctionality

| Field           | Value                                                     |
| --------------- | --------------------------------------------------------- |
| Element Name    | ik:multifunctionality                                     |
| Label           | Multifunctionality                                        |
| URI             | https://nhk.singlepersonhousehold/ikea/multifunctionality |
| Full Definition | Versatility and multi-functionality                       |
| Data Values     | String (Description)                                      |
| Cardinality     | Mandatory, Non-repeatable                                 |
| Comments        | This is the criterion for assessing space-saving efficiency for single-person households.                                                                   |
| Example         |Bed, Sofa, and Storage                                     |

### ik:spaceEfficiency

| Field           | Value                                                  |
| --------------- | ------------------------------------------------------ |
| Element Name    | ik:spaceEfficiency                                     |
| Label           | Space Efficiency                                       |
| URI             | https://nhk.singlepersonhousehold/ikea/spaceefficiency |
| Full Definition | Suitability for small spaces                           |
| Data Values     | Controlled Vocabulary                                  |
| Cardinality     | Mandatory, Repeatable                                  |
| Comments        | Categorizes the specific ways this furniture secures space in the cramped living environments of single-person households.                           |
| Example         | WallMounted                                            |

### ik:weight

| Field           | Value                                             |
| --------------- | ------------------------------------------------- |
| Element Name    | ik:weight                                         |
| Label           | Weight                                            |
| URI             | https://nhk.singlepersonhousehold/ikea/weight     |
| Full Definition | Product weight(unit: kg)                          |
| Data Values     | Decimal                                           |
| Cardinality     | Mandatory, Non-repeatable                         |
| Comments        | Refer to IKEA website.                            |
| Example         | 34.5                                              |

### ik:relatedItems

| Field           | Value                                                                       |
| --------------- | --------------------------------------------------------------------------- |
| Element Name    | ik:relatedItems                                                             |
| Label           | Related Items                                                               |
| URI             | https://nhk.singlepersonhousehold/ikea/relatedItems                         |
| Full Definition | List of identifiers for related products that are suitable for use with an object                                                                                          |
| Data Values     | String                                                                      |
| Cardinality     | Non-mandatory, Repeatable                                                   |
| Comments        | Enter the recommended product's dc:identifier to ensure data connectivity + The product name must be provided in the label attribute so that it can be identified by users. |
| Example         | label="FRÖSVI folding chair" , 505.610.41                                   |

### ik:url

| Field           | Value                                             |
| --------------- | ------------------------------------------------- |
| Element Name    | ik:url                                            |
| Label           | IKEA Webpage URL                                  |
| URI             | https://nhk.singlepersonhousehold/ikea/url        |
| Full Definition | URL of the item.                                  |
| Data Values     | URI (xs:anyURI)                                   |
| Cardinality     | Mandatory, Non-repeatable                         |
| Comments        | Provide the URL of the official IKEA product page. This allows users to access detailed product information, images, and purchasing options.         |
| Example         | https://www.ikea.com/kr/ko/p/skubb-clothes-cover-set-of-3-white-30179464 |
