---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web",
    "a": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller chooses an external provider reference and accepts valid prepared component information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
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
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The Product consults the separately addressed provider activity configuration for the selected provider path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "product-settings",
          "effect": "reads",
          "facts": [
            "Provider activity configuration"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The Product retrieves external detail information and prepares the accepted component form.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The Product saves the accepted Part information and carries the caller into the ordinary editor.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part",
          "effect": "creates",
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
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "create-part-from-info-provider"
    },
    {
      "text": "The caller supplies valid changes to the selected record’s supported information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "edit-part"
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
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "edit-part"
    },
    {
      "text": "The Product saves the supplied Part information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Comment",
            "Manufacturer product number",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "edit-part"
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
      "target": "src/Controller/InfoProviderController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/InfoProviderSystem/ProviderRegistry.php"
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

# Create part and edit provider achieved

## Trigger

The same caller follows the source-carried continuation: Saved Part reaches its ordinary editor.

## Outcome

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
