# 📐 PROCUX API Schemas

[![PROCUX](https://img.shields.io/badge/PROCUX-Decision_Infrastructure-000000?style=flat-square)](https://procux.com)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-3.1-6BA539?style=flat-square&logo=openapi-initiative&logoColor=white)]()
[![JSON Schema](https://img.shields.io/badge/JSON_Schema-Draft_2020--12-000000?style=flat-square)]()
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)

> OpenAPI specifications, JSON Schemas, and shared data models for the PROCUX B2B decision infrastructure.

---

## 📦 What's Inside

```
procux-schemas/
├── openapi/
│   ├── collective-purchasing-v1.yaml   # Collective purchasing API
│   ├── supplier-portal-v1.yaml        # Supplier integration API
│   └── webhook-events-v1.yaml         # Webhook event definitions
├── schemas/
│   ├── demand-pool.json               # Demand pooling data model
│   ├── rfq.json                       # RFQ (Request for Quotation)
│   ├── supplier-profile.json          # Supplier entity schema
│   ├── order.json                     # Order lifecycle model
│   ├── product-category.json          # Product taxonomy
│   └── ai-recommendation.json         # AI agent output schema
├── enums/
│   ├── order-status.json              # Order state machine
│   ├── rfq-status.json                # RFQ lifecycle states
│   └── user-roles.json                # Platform user roles
└── examples/
    ├── create-demand.json             # Example: create demand request
    ├── rfq-response.json              # Example: supplier RFQ response
    └── webhook-payload.json           # Example: webhook event payload
```

---

## 🔄 Core Data Models

### Demand Pool
The fundamental unit of collective purchasing. Individual demands aggregate into pools, triggering automated RFQ dispatch at daily cutoff.

### RFQ (Request for Quotation)
Generated automatically from demand pools. Dispatched to qualified suppliers with volume-based pricing tiers.

### AI Recommendation
Structured output from AI agents — includes decision rationale, confidence score, data sources, and alternative options.

---

## 🛠️ Usage

**Validate against schemas:**
```bash
# Using ajv-cli
npx ajv validate -s schemas/demand-pool.json -d your-data.json

# Using Python jsonschema
python -m jsonschema -i your-data.json schemas/demand-pool.json
```

**Generate types from OpenAPI:**
```bash
# TypeScript
npx openapi-typescript openapi/collective-purchasing-v1.yaml -o types/api.ts

# Python (Pydantic)
datamodel-codegen --input openapi/collective-purchasing-v1.yaml --output models.py
```

---

## 🤝 Contributing

We welcome contributions to improve schema definitions and documentation. Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## 📬 Contact

- **Website:** [procux.com](https://procux.com)
- **Email:** info@procux.com

---

## 📄 License

[MIT](LICENSE)
