---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller opens the collection and selects from the available record identities.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-supplier"
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
          "place": "web::public::public-supplier"
        }
      }
    },
    {
      "text": "The Product returns the available Supplier identities and names in their parent/child grouping.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "supplier",
          "effect": "reads",
          "facts": [
            "Name",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-supplier"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Supplier.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/SupplierController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/Trees/TreeViewGenerator.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Repository/StructuralDBElementRepository.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/admin/base_admin.html.twig"
    }
  ]
}
---

# Browse suppliers — Public Web primary

## Trigger

The caller opens the collection and selects from the available record identities.

## Outcome

The collection discloses the available identities and names; a selected record has its separate detail case.
