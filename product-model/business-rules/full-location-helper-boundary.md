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

# Helper addition refuses a full target location

Helper addition refuses a target whose Location is Full. This check does not imply that every lot-form occupancy restriction is run by the helper. A movement target uses the same helper eligibility check.
