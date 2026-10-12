---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The supplied local credentials are invalid; no accepted local session is established.",
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
      "text": "The Product does not complete sign in because the supplied local credentials are invalid; no accepted local session is established.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Sign in — Public Web invalid input

## Trigger

The supplied local credentials are invalid; no accepted local session is established.

## Outcome

The supplied local credentials are invalid; no accepted local session is established. No successful sign in result is asserted.
