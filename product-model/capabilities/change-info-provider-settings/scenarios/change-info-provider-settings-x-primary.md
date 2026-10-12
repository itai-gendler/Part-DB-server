---
{
  "kind": "primary",
  "routes": {
    "route": "Administration Web"
  },
  "steps": [
    {
      "text": "The caller submits valid replacement values for Information-provider options on the selected record.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::administration::system-settings"
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
          "place": "web::administration::system-settings"
        }
      }
    },
    {
      "text": "The Product validates, merges and saves the supplied section, then reaches its cache invalidation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "product-settings",
          "effect": "changes",
          "facts": [
            "Information-provider options"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::administration::system-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Settings/AppSettings.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/SettingsController.php"
    }
  ]
}
---

# Change info provider settings — x primary

## Trigger

The caller submits valid replacement values for Information-provider options on the selected record.

## Outcome

General provider section saved
