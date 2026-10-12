---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests movement from a known source to an existing destination whose quantity is unknown.",
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
      "text": "The Product checks the effective source balance and the relative-adjustment eligibility of both selected lots.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Amount",
            "Unknown amount",
            "Location assignment"
          ],
          "as": "source"
        },
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Unknown amount",
            "Location assignment"
          ],
          "as": "target"
        },
        {
          "entity": "storage-location",
          "effect": "reads",
          "facts": [
            "Full"
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
      "text": "The Product stops the transfer at the failing helper boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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
      "target": "src/Form/Part/PartLotType.php"
    }
  ]
}
---

# Move stock — Unknown source/target or full target prevents movement (Public Web)

## Trigger

The caller requests movement from a known source to an existing destination whose quantity is unknown.

## Outcome

Unknown source/target quantity or a full target prevents transfer; no universal error envelope is promised.
