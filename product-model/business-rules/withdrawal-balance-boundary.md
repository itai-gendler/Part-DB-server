---
{
  "appliesTo": [
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

# Effective withdrawal cannot exceed known balance

Effective rounded withdrawal or movement quantity cannot exceed the known source balance. Expiration alone does not prohibit addition or withdrawal.
