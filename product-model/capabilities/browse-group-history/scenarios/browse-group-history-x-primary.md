---
{
  "kind": "primary",
  "routes": {
    "route": "Administration Web"
  },
  "steps": [
    {
      "text": "The caller requests matching activity record information through this contract’s supported selection.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::administration::group-administration"
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
          "place": "web::administration::group-administration"
        }
      }
    },
    {
      "text": "The Product returns the recorded events and supported historical reconstruction for the selected subject.",
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
        },
        {
          "entity": "group",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
            "Enforce second factor",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::administration::group-administration"
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

# Browse group history — x primary

## Trigger

The caller requests matching activity record information through this contract’s supported selection.

## Outcome

The requested history is available as disclosure; no persisted revert is performed.
