---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller selects an existing recorded event and supplies valid confirmation.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-activity-entry"
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
          "place": "web::authenticated::authenticated-activity-entry"
        }
      }
    },
    {
      "text": "The Product removes the selected Activity entry through this contract’s implemented path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "activity-entry",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-activity-entry"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/LogSystem/AbstractLogEntry.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/LogController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/LogSystem/TimeTravel.php"
    }
  ]
}
---

# Delete activity entry — Authenticated Web primary

## Trigger

The caller selects an existing recorded event and supplies valid confirmation.

## Outcome

Entry removed
