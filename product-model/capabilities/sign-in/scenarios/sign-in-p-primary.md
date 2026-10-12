---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits valid local credentials for an enabled account.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::sign-in"
        }
      }
    },
    {
      "text": "The Product checks the User credential and account eligibility, then establishes the local session or required continuation.",
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
        "route": {
          "place": "web::public::sign-in"
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
      "target": "src/Controller/SecurityController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserSystem/PasswordResetManager.php"
    }
  ]
}
---

# Sign in — Public Web primary

## Trigger

The caller submits valid local credentials for an enabled account.

## Outcome

Local authentication is accepted; required password change leads into its separate capability.
