---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests export components through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part-list"
        }
      }
    },
    {
      "text": "The Product stops the requested export component operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part-list"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartImportExportController.php"
    }
  ]
}
---

# Export parts — Public Web refusal

## Trigger

The caller requests export parts and reaches its closed entry or disabled-control result.

## Outcome

The requested export parts result is withheld; no accepted change or removal of the requested subject is produced.
