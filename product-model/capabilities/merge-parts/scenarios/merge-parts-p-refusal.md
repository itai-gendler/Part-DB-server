---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests merge components through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
        }
      }
    },
    {
      "text": "The Product stops the requested merge component operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Merge parts — Public Web refusal

## Trigger

The caller requests merge parts and reaches its closed entry or disabled-control result.

## Outcome

The requested merge parts result is withheld; no accepted change or removal of the requested subject is produced.
