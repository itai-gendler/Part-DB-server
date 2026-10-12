---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The old password is incorrect or the new passwords mismatch or violate the declared length.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::personal-settings"
        }
      }
    },
    {
      "text": "The Product retains the form’s validation errors for the old password is incorrect or the new passwords mismatch or violate the declared length. The submitted write is not accepted.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::personal-settings"
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
    }
  ]
}
---

# Change password — Authenticated Web invalid input

## Trigger

The old password is incorrect or the new passwords mismatch or violate the declared length.

## Outcome

The old password is incorrect or the new passwords mismatch or violate the declared length. No successful change password result is asserted.
