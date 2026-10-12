---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller selects an existing recorded event.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-activity-entry"
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
          "place": "web::public::public-activity-entry"
        }
      }
    },
    {
      "text": "The Product reads the selected Activity entry and returns its formatted details.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "activity-entry",
          "effect": "reads",
          "facts": [
            "Actor name",
            "Occurred at",
            "Event kind",
            "Severity",
            "Access method",
            "Target reference",
            "Event details",
            "Request correlation",
            "Transaction correlation"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-activity-entry"
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

# Read activity entry — Public Web primary

## Trigger

The caller selects an existing recorded event.

## Outcome

Selected details disclosed
