---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits a positive requirement quantity with a component reference or free-text name and valid mount names.",
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
      "text": "The Product saves the new BOM entry with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "bom-entry",
          "effect": "creates",
          "facts": [
            "Name",
            "Comment",
            "Quantity",
            "Mount names",
            "Price",
            "Project assignment",
            "Part assignment",
            "Price Currency assignment",
            "Added at",
            "Modified at"
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

# Create bom entry — REST primary

## Trigger

The caller submits a positive requirement quantity with a component reference or free-text name and valid mount names.

## Outcome

Linked/free-text entry added
