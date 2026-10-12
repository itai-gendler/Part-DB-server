---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller requests matching package outline information through this contract’s supported selection.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "api-client",
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
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product discloses matching Footprint information through this contract.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "footprint",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
            "Preview attachment",
            "Added at",
            "Modified at",
            "EDA information",
            "3D attachment selection",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "rest-api"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/AbstractStructuralDBElement.php"
    }
  ]
}
---

# Browse footprints — REST primary

## Trigger

The caller requests matching package outline information through this contract’s supported selection.

## Outcome

Matching Footprint records are disclosed.
