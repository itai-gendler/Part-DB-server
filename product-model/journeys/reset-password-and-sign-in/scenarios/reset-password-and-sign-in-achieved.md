---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests recovery for an eligible known account, then redeems its valid credential with a matching new password.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::password-reset"
        }
      },
      "capability": "reset-password"
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
        "p": {
          "place": "web::public::password-reset"
        }
      },
      "capability": "reset-password"
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
        "p": {
          "place": "web::public::password-reset"
        }
      },
      "capability": "reset-password"
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
        "p": {
          "place": "web::public::password-reset"
        }
      },
      "capability": "reset-password"
    },
    {
      "kind": "product",
      "actor": "user",
      "text": "The Product carries the caller to local sign-in after accepted recovery.",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::password-reset"
        }
      },
      "capability": "reset-password"
    },
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
        "p": {
          "place": "web::public::sign-in"
        }
      },
      "capability": "sign-in"
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

# Reset password and sign in achieved

## Trigger

The same caller follows the source-carried continuation: Successful recovery → sign-in using recovered credential.

## Outcome

The recovered credential is accepted by local sign-in.
