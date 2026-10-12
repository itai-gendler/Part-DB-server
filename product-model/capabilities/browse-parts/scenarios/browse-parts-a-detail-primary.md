---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests the supported information of one existing selected record.",
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
      "text": "The Product discloses the selected Part information through this contract.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Comment",
            "Tags",
            "Internal part number",
            "GTIN",
            "Manufacturer product number",
            "Manufacturer URL",
            "Manufacturing status",
            "Minimum desired amount",
            "Favorite",
            "Needs review",
            "Mass",
            "EDA information",
            "Provider reference",
            "Preview attachment",
            "Category assignment",
            "Footprint assignment",
            "Manufacturer assignment",
            "Unit assignment",
            "Custom state assignment",
            "Added at",
            "Modified at",
            "Stock summary"
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
      "target": "src/Entity/Parts/Part.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Browse parts — Authenticated Web detail primary

## Trigger

One existing subject is selected for its detail information.

## Outcome

Matching Parts disclosed through the relevant projection
