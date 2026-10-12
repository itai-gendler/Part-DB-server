---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller redeems valid recovery data for an account with Password change required already set.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::password-reset"
        }
      }
    },
    {
      "text": "The Product accepts valid User recovery redemption, changes the credential and invalidates recovery data.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
            "Password credential",
            "Reset credential verifier",
            "Reset credential expiry",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::password-reset"
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

# Reset password — Successful recovery leaves Password change required unchanged (Public Web)

## Trigger

The caller redeems valid recovery data for an account with Password change required already set.

## Outcome

Successful recovery leaves Password change required unchanged; required-password change remains a distinct continuation.
