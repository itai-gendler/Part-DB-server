---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller selects an existing destination for the same component and requests movement of two units with a comment.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
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
          "place": "web::authenticated::authenticated-part"
        }
      }
    },
    {
      "text": "The Product resolves the source and existing destination and checks their quantities and component assignments.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Amount",
            "Unknown amount",
            "Part assignment",
            "Location assignment",
            "Owner assignment"
          ],
          "as": "source"
        },
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Amount",
            "Unknown amount",
            "Part assignment",
            "Location assignment",
            "Owner assignment"
          ],
          "as": "target"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    },
    {
      "text": "The Product decreases the source and increases the destination by the effective quantity, then reaches the caller’s flush.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "changes",
          "facts": [
            "Amount",
            "Modified at"
          ],
          "as": "source"
        },
        {
          "entity": "part-lot",
          "effect": "changes",
          "facts": [
            "Amount",
            "Modified at"
          ],
          "as": "target"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartLot.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/Parts/PartLotWithdrawAddHelper.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Security/Voter/PartLotVoter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartLotStockProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/TimestampTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/Part/PartLotType.php"
    }
  ]
}
---

# Move stock — Authenticated Web primary

## Trigger

The caller selects an existing destination for the same component and requests movement of two units with a comment.

## Outcome

The accepted transfer is saved between the selected lots of the same Part; the source and existing target have their distinct checks.

## Edge cases

- Helper failures do not imply locking, race-free accounting or atomic rollback.
- An omitted MCP comment becomes an empty string; Web omitted-comment boundaries are separate cases.
