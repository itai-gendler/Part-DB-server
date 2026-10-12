---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller selects the existing package outline for removal with valid confirmation or reference input.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-footprint"
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
          "place": "web::authenticated::authenticated-footprint"
        }
      }
    },
    {
      "text": "The Product removes the selected Footprint through this contract’s implemented path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "footprint",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-footprint"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Footprint.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/FootprintController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Delete footprint — Authenticated Web primary

## Trigger

The caller selects the existing package outline for removal with valid confirmation or reference input.

## Outcome

The selected Footprint is removed through the implemented deletion path.
