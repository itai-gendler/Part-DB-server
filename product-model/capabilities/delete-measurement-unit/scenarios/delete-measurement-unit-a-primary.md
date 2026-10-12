---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller selects the existing quantity unit for removal with valid confirmation or reference input.",
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
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      }
    },
    {
      "text": "The Product removes the selected Measurement unit through this contract’s implemented path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "measurement-unit",
          "effect": "removes"
        }
      ],
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

# Delete measurement unit — Authenticated Web primary

## Trigger

The caller selects the existing quantity unit for removal with valid confirmation or reference input.

## Outcome

The selected Measurement unit is removed through the implemented deletion path.
