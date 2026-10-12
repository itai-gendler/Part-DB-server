---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests that the current session or pending authentication be cleared.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public"
        }
      }
    },
    {
      "text": "The Product clears the current session or pending authentication while the caller remains attributed to its current context.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public"
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

# Sign out — Public Web primary

## Trigger

The caller requests that the current session or pending authentication be cleared.

## Outcome

The session or pending authentication is cleared.
