---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits valid local credentials for an enabled account.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "The Product accepts local authentication and carries the caller into required password change.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Username",
            "Password credential",
            "Disabled",
            "Password change required"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::sign-in"
        }
      },
      "capability": "sign-in"
    },
    {
      "text": "The caller supplies the correct old password and a matching valid new password.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::authenticated::personal-settings"
        }
      },
      "capability": "change-password"
    },
    {
      "text": "The Product checks the User password input and saves the new credential while clearing the required-change flag.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
            "Password credential",
            "Password change required",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::authenticated::personal-settings"
        }
      },
      "capability": "change-password"
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
      "target": "src/Controller/SecurityController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserSystem/PasswordResetManager.php"
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
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Sign in and change required password achieved

## Trigger

The same caller follows the source-carried continuation: Sign-in → required password change; required flag cleared.

## Outcome

The required password change saves the new credential and clears Password change required.
