---
{
  "actors": [
    "user"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/SecurityController.php"
    }
  ]
}
---

# Sign in and change required password

## Goal

Sign-in → required password change; required flag cleared.

## Success criterion

The required password change saves the new credential and clears Password change required.
