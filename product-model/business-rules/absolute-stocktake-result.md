---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "stocktake-part-lot",
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

# Absolute stocktaking replaces quantity, clears unknown and sets time

An accepted absolute count replaces Amount, clears Unknown amount and sets Last stocktake. Zero is accepted and dated; counting alone does not request cleanup.
