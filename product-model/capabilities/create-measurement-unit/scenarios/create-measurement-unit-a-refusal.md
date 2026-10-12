---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests create quantity unit through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-measurement-unit"
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
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/MeasurementUnit.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/MeasurementUnitController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Create measurement unit — Authenticated Web refusal

## Trigger

The caller requests create measurement unit and reaches its closed entry or disabled-control result.

## Outcome

The creation controls remain disabled and no new Measurement unit is established; a uniform explicit server create-denial check is not asserted.
