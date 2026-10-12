---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The supplied CAPTCHA, password pair, recovery verifier or recovery expiry is invalid.",
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
      "text": "The Product does not complete reset password because the supplied CAPTCHA, password pair, recovery verifier or recovery expiry is invalid.",
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

# Reset password — Public Web invalid input

## Trigger

The supplied CAPTCHA, password pair, recovery verifier or recovery expiry is invalid.

## Outcome

The supplied CAPTCHA, password pair, recovery verifier or recovery expiry is invalid. No successful reset password result is asserted.
