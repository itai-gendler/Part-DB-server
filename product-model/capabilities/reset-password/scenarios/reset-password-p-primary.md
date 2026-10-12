---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests recovery for an eligible known account, then redeems its valid credential with a matching new password.",
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
      "text": "The Product stores recovery verification and expiry for the eligible User.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
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
    },
    {
      "text": "The Product sends the recovery link when the account has an email address.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Personal profile",
            "Reset credential expiry"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::password-reset"
        }
      }
    },
    {
      "text": "The Product accepts the valid redemption, changes the credential and invalidates the recovery data.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Reset password — Public Web primary

## Trigger

The caller requests recovery for an eligible known account, then redeems its valid credential with a matching new password.

## Outcome

The recovered credential can be used for sign-in; the existing required-password-change flag is unchanged.
