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
          "place": "web::administration::user-administration"
        }
      }
    },
    {
      "text": "The Product returns the available User identities and usernames.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Username"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::administration::user-administration"
        }
      }
    },
    {
      "text": "The Product returns the available User identities and usernames.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Username"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::administration::user-administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/UserSystem/User.php"
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
      "target": "src/Repository/NamedDBElementRepository.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/admin/base_admin.html.twig"
    }
  ]
}
---

# Browse users — x primary

## Trigger

The caller opens the collection and selects from the available record identities.

## Outcome

The collection discloses the available identities and names; a selected record has its separate detail case.
