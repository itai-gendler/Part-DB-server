---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "add-stock",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "capability",
      "id": "withdraw-stock",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "capability",
      "id": "move-stock",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/Parts/PartLotWithdrawAddHelper.php"
    }
  ]
}
---

# Relative adjustments require known quantity

Relative addition, withdrawal and movement require known quantities on their applicable lot instances; unknown stock is not treated as a numeric zero.
