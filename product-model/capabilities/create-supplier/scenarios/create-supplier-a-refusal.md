---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests create vendor record through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-supplier"
        }
      }
    },
    {
      "text": "The Product retains the disabled creation controls and no accepted creation is performed.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-supplier"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Supplier.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/SupplierController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Create supplier — Authenticated Web refusal

## Trigger

The caller requests create supplier and reaches its closed entry or disabled-control result.

## Outcome

The creation controls remain disabled and no new Supplier is established; a uniform explicit server create-denial check is not asserted.
