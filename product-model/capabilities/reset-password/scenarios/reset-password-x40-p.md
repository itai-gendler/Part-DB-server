---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests password recovery for an identification that matches no account.",
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
      "text": "The Product acknowledges the unknown-account recovery request without creating recovery data for a found account.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Reset password — Unknown account receives request acknowledgment without credential change (Public Web)

## Trigger

The caller requests password recovery for an identification that matches no account.

## Outcome

The acknowledgment does not reveal account existence and changes no User credential.
