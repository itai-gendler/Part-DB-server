---
{
  "entities": [
    {
      "entity": "user",
      "shows": [
        "Username",
        "Personal profile",
        "Preferences",
        "Password change required",
        "Disabled",
        "SAML account",
        "Added at",
        "Modified at"
      ]
    },
    {
      "entity": "group",
      "shows": [
        "Name",
        "Comment"
      ]
    },
    {
      "entity": "activity-entry",
      "shows": [
        "Actor name",
        "Occurred at",
        "Event kind",
        "Severity",
        "Access method",
        "Target reference",
        "Event details",
        "Request correlation",
        "Transaction correlation"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/UserController.php"
    }
  ]
}
---

# User administration

Inspected account information, group membership and supported history.
