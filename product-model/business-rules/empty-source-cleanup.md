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

# Requested zero-balance cleanup removes the source

Requested withdrawal/movement cleanup removes the source when its resulting amount is exactly zero. Stocktaking alone has no implicit cleanup; authorized cleanup does not add a standalone deletion voter.
