---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests withdrawal of two units from a known balance of at least two and supplies a comment.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
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
          "place": "web::public::public-part"
        }
      }
    },
    {
      "text": "The Product resolves the selected Part lot and reads its quantity, ownership and location information.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Amount",
            "Unknown amount",
            "Owner assignment",
            "Location assignment",
            "Part assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
        }
      }
    },
    {
      "text": "The Product decreases the known quantity by the effective positive withdrawal and reaches the caller’s flush.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "changes",
          "facts": [
            "Amount",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
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

# Withdraw stock — Public Web primary

## Trigger

The caller requests withdrawal of two units from a known balance of at least two and supplies a comment.

## Outcome

The accepted withdrawal decreases the saved quantity without requiring expiration to be in the future.

## Edge cases

- Helper failures do not imply locking, race-free accounting or atomic rollback.
- An omitted MCP comment becomes an empty string; Web omitted-comment boundaries are separate cases.
