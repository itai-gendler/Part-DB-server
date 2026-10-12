---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests addition to a known stock lot whose storage place is marked Full.",
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
      "text": "The Product reads the Storage location’s Full flag and rejects the helper addition.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-location",
          "effect": "reads",
          "facts": [
            "Full"
          ]
        },
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "Unknown amount",
            "Location assignment"
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
      "target": "src/Form/Part/PartLotType.php"
    }
  ]
}
---

# Add stock — Full location prevents helper addition (Public Web)

## Trigger

The caller requests addition to a known stock lot whose storage place is marked Full.

## Outcome

The full target prevents helper addition, without implying that every occupancy-validator restriction is checked by this helper.
