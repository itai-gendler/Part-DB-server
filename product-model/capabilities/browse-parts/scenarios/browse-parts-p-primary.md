---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests matching component information through this contract’s supported selection.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part-list"
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
          "place": "web::public::public-part-list"
        }
      }
    },
    {
      "text": "The Product discloses matching Part information through this contract.",
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
          "place": "web::public::public-part-list"
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

# Browse parts — Public Web primary

## Trigger

The caller requests matching component information through this contract’s supported selection.

## Outcome

Matching Parts disclosed through the relevant projection
