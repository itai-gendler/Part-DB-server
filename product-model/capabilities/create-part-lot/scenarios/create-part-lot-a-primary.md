---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits a description, a known initial quantity of two and a valid enclosing component reference.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::authenticated-part"
        }
      }
    },
    {
      "text": "The Product saves the new Part lot with its supplied information and source-supported defaults.",
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
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
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
    }
  ]
}
---

# Create part lot — Authenticated Web primary

## Trigger

The caller submits a description, a known initial quantity of two and a valid enclosing component reference.

## Outcome

New lot linked and saved
