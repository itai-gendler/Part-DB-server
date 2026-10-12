---
{
  "kind": "primary",
  "routes": {
    "route": "Administration Web"
  },
  "steps": [
    {
      "text": "The caller requests the supported information of one existing selected record.",
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
      "text": "The Product discloses the selected Group information through this contract.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "group",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
            "Enforce second factor",
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
    }
  ]
}
---

# Browse groups — x detail primary

## Trigger

One existing subject is selected for its detail information.

## Outcome

Inspected administration information disclosed
