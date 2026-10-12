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
          "place": "web::authenticated::authenticated-manufacturer"
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
          "place": "web::authenticated::authenticated-manufacturer"
        }
      }
    },
    {
      "text": "The Product discloses the selected Manufacturer information through this contract.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "manufacturer",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
            "Not selectable",
            "Alternative names",
            "Preview attachment",
            "Added at",
            "Modified at",
            "Address",
            "Phone",
            "Fax",
            "Email",
            "Website",
            "Product URL template"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-manufacturer"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Manufacturer.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/ManufacturerController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Browse manufacturers — Authenticated Web detail primary

## Trigger

One existing subject is selected for its detail information.

## Outcome

Matching Manufacturer records are disclosed.
