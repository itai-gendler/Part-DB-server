---
{
  "kind": "edge",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller requests labels for a mixture of existing and missing target identifiers.",
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
      "text": "The Product resolves supplied saved Label profile options and reads the subset of requested Part targets actually found.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "label-profile",
          "effect": "reads",
          "facts": [
            "Options"
          ]
        },
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name",
            "Description"
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
      "text": "The Product returns generated output for the nonempty found subset.",
      "kind": "product",
      "actor": "api-client",
      "entities": [],
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
      "target": "src/Entity/LabelSystem/LabelProfile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/LabelProfileController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Generate labels — Found IDs can be processed when others are missing; wholly absent targets fail (REST)

## Trigger

The caller requests labels for a mixture of existing and missing target identifiers.

## Outcome

Some missing IDs do not prevent processing a nonempty found set; a wholly absent target set fails.
