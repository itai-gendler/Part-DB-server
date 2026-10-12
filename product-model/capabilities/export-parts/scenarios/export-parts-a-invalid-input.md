---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The requested selection or representation cannot be accepted by the export path.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part-list"
        }
      }
    },
    {
      "text": "The Product does not complete export components because the requested selection or representation cannot be accepted by the export path.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part-list"
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

# Export parts — Authenticated Web invalid input

## Trigger

The requested selection or representation cannot be accepted by the export path.

## Outcome

The requested selection or representation cannot be accepted by the export path. No successful export parts result is asserted.
