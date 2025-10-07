# Icecream Shops XML + DTD

XML + DTD project describing ice cream shops, their employees and sales (ice creams and smoothies).

This project defines:

- `icecreams.xml` — an XML document that stores real data of ice cream shops, employees, and their sales.
- `icecream.dtd` — a DTD that enforces the valid structure for the XML file.

---

## Table of Contents
- [About the Project](#about-the-project)
- [Features](#features)
- [Files](#files)
- [Requirements](#requirements)
- [Installation & Validation](#installation--validation)
- [Usage](#usage)
- [Structure](#structure)
- [Contributing](#contributing)
- [Authors](#authors)
- [Acknowledgements](#acknowledgements)
- [License](#license)

---

## About the Project
This project models an ice cream shop chain.  
Each shop has a `shopid` and `direction`, a list of employees, and each employee records the sales they have made.  
Products include ice creams (with ball count, flavors, size, type, optional extras and price) and smoothies (with flavor, size, amount and price).

The included DTD (`icecream.dtd`) defines the allowed structure, elements and attributes for the XML document to ensure its consistency and validity.

---

## Features
- Valid XML structure for multiple ice cream shops.
- Enforces correct element order and attributes with a DTD.
- Supports two product types: **icecream** and **smoothiee**.
- Optional extra fields like `add` for toppings.

---

## Files
- `icecreams.xml` — Example XML file containing shop, employee and sales data.  
- `icecream.dtd` — DTD describing valid structure of the XML.  
- `README.md` — this documentation.  

---

## Requirements
- Any XML editor (VS Code, Oxygen XML, XMLSpy, Notepad++).
- XML validator like `xmllint`.

---

## Installation & Validation

### Install `xmllint` on Ubuntu/Debian:
```bash
sudo apt update
sudo apt install libxml2-utils
```

### Validate XML against the DTD:
```bash
xmllint --noout --dtdvalid icecream.dtd icecreams.xml
```

---

## Usage

### Pretty print the XML:
```bash
xmllint --format icecreams.xml
```

### Example XML snippet:
```xml
<!DOCTYPE icecreamsshops SYSTEM "icecream.dtd">
<icecreamsshops>
  <icecreamshop shopid="001" direction="Plaza españa S/N">
    <employeeds>
      <employeed id="44775543K">
        <sales>
          <icecream ball="3">
            <flavor>chocolate, vanilla, lemon</flavor>
            <size>medium</size>
            <amount>1</amount>
            <type>cone</type>
            <add>syrup</add>
            <price>4.95</price>
          </icecream>
        </sales>
      </employeed>
    </employeeds>
  </icecreamshop>
</icecreamsshops>
```

---

## Structure

### Root:
- `icecreamsshops` — contains one or more `icecreamshop`.

### Shop:
- `icecreamshop` — attributes:
  - `shopid` (required): unique shop identifier.
  - `direction` (required): address.
  Contains `employeeds`.

### Employees:
- `employeeds` — container for one or more `employeed`.
- `employeed` — attribute `id` (required): employee identifier.
  Contains `sales` (optional).

### Sales:
- `sales` — contains zero or more `icecream` and `smoothiee` elements.

### Products:
- `icecream` — attribute:
  - `ball` (required): number of scoops.
  Child elements in order:
  - `flavor` — text (comma-separated flavors).
  - `size` — text (small, medium…).
  - `amount` — integer.
  - `type` — text (cone, cup…).
  - `add` — optional extra/topping.
  - `price` — decimal price.

- `smoothiee` — child elements:
  - `flavor` — text (one or more flavors).
  - `size` — text.
  - `amount` — integer.
  - `price` — decimal price.

### Other Elements:
- `flavor`, `size`, `amount`, `type`, `add`, `price` — all contain `#PCDATA`.

---

## Contributing
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

---

## Authors
- **Jonathan Lara**  
- **Victor Garcia**

---

## Acknowledgements
- Thanks to **Heladería Amorino** for inspiration and support.  
- Thanks to **El Niño Jesús** for blessings and guidance.  

---

## License
MIT License © 2025 Jonathan Lara & Victor Garcia  
See `LICENSE` for details.
