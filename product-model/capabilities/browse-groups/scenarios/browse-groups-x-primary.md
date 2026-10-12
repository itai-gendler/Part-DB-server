---
{
  "kind": "primary",
  "routes": {
    "route": "Administration Web"
  },
  "steps": [
    {
      "text": "The caller opens the collection and selects from the available record identities.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::administration::group-administration"
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
          "place": "web::administration::group-administration"
        }
      }
    },
    {
      "text": "The Product returns the available Group identities and names in their parent/child grouping.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "group",
          "effect": "reads",
          "facts": [
            "Name",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::administration::group-administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/UserSystem/Group.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/UserSettingsController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/UserController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/GroupController.php"
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

# Browse groups — x primary

## Trigger

The caller opens the collection and selects from the available record identities.

## Outcome

The collection discloses the available identities and names; a selected record has its separate detail case.
