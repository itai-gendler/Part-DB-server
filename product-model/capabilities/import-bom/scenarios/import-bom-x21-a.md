---
{
  "kind": "edge",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller imports requirements with clearing enabled, and later file parsing or field mapping fails.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-bom-import"
        }
      }
    },
    {
      "text": "The Product clears existing BOM entry records and reaches that clearing flush before parsing the later invalid input.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "bom-entry",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-bom-import"
        }
      }
    },
    {
      "text": "The Product then encounters the parse or mapping failure.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-bom-import"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/ProjectSystem/ProjectBOMEntry.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/ProjectController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/ProjectSystem/ProjectBuildHelper.php"
    }
  ]
}
---

# Import bom — Existing-entry clearing may be flushed before later parse/mapping failure (Authenticated Web)

## Trigger

The caller imports requirements with clearing enabled, and later file parsing or field mapping fails.

## Outcome

Previously existing entries may already be removed when later import processing fails; atomic replacement is not guaranteed.
