---
{
  "kind": "validation",
  "routes": {
    "route": "Administration Web"
  },
  "steps": [
    {
      "text": "The caller requests browse account groupings through this contract.",
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
      "text": "The Product stops the requested browse account grouping operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Browse groups — x refusal

## Trigger

The caller requests browse groups and reaches its closed entry or disabled-control result.

## Outcome

The requested browse groups result is withheld; no accepted change or removal of the requested subject is produced.
