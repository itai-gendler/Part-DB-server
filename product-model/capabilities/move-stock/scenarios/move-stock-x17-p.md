---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests valid movement into a new destination whose supplied initial quantity is positive.",
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
      "text": "The Product saves the new Part lot destination with its supported supplied initial quantity.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "creates",
          "facts": [
            "Description",
            "Comment",
            "Amount",
            "Unknown amount",
            "Needs refill",
            "Expiration date",
            "User barcode",
            "Last stocktake",
            "Part assignment",
            "Location assignment",
            "Owner assignment",
            "Added at",
            "Modified at"
          ],
          "as": "target"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
        }
      }
    },
    {
      "text": "The Product decreases the source and adds the effective transfer to the new destination’s existing initial quantity.",
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
            "Amount"
          ],
          "as": "target"
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
      "target": "src/Form/Part/PartLotType.php"
    }
  ]
}
---

# Move stock — New target’s supported initial quantity is increased, rather than assumed zero (Public Web)

## Trigger

The caller requests valid movement into a new destination whose supplied initial quantity is positive.

## Outcome

The resulting destination quantity includes both its supplied initial quantity and the transfer; a zero initial quantity is not assumed.
