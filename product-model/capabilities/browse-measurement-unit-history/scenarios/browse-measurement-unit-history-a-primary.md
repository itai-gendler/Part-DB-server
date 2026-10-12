---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests matching activity record information through this contract’s supported selection.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-measurement-unit"
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
          "place": "web::authenticated::authenticated-measurement-unit"
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
          "entity": "measurement-unit",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
            "Not selectable",
            "Alternative names",
            "Preview attachment",
            "Added at",
            "Modified at",
            "Unit symbol",
            "Integer amounts",
            "SI prefixes"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-measurement-unit"
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

# Browse measurement unit history — Authenticated Web primary

## Trigger

The caller requests matching activity record information through this contract’s supported selection.

## Outcome

The requested history is available as disclosure; no persisted revert is performed.
