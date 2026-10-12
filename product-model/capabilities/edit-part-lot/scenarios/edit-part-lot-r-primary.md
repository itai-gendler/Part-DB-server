---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits valid replacement values for Description, Comment, Unknown amount, Needs refill, Expiration date, Location assignment, Owner assignment, account barcode on the selected record.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "api-client",
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
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product saves the supplied Part lot information through the implemented write.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "changes",
          "facts": [
            "Description",
            "Comment",
            "Unknown amount",
            "Needs refill",
            "Expiration date",
            "Location assignment",
            "Owner assignment",
            "User barcode",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "rest-api"
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
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Edit part lot — REST primary

## Trigger

The caller submits valid replacement values for Description, Comment, Unknown amount, Needs refill, Expiration date, Location assignment, Owner assignment, account barcode on the selected record.

## Outcome

Supported metadata saved
