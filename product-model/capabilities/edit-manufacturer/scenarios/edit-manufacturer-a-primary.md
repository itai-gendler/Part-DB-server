---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits valid replacement values for Name, Comment on the selected record.",
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
      "text": "The Product saves the supplied Manufacturer information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "manufacturer",
          "effect": "changes",
          "facts": [
            "Name",
            "Comment",
            "Modified at"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Edit manufacturer — Authenticated Web primary

## Trigger

The caller submits valid replacement values for Name, Comment on the selected record.

## Outcome

Supplied Manufacturer changes are saved.
