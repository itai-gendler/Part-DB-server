---
{
  "appliesTo": [
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

# Movement requires the same component but not distinct lot identities

Movement requires source and destination to refer to the same Part. There is no explicit distinct-lot check; an eligible same-instance transfer subtracts then adds with no net balance change.
