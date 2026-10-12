---
{
  "entities": [
    {
      "entity": "user",
      "shows": [
        "Username",
        "Personal profile",
        "Preferences",
        "Password change required"
      ],
      "collects": [
        "Username",
        "Personal profile",
        "Preferences",
        "Password credential"
      ]
    },
    {
      "entity": "api-token",
      "shows": [
        "Name",
        "Permission level",
        "Expires at",
        "Last used at",
        "Added at"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/UserSettingsController.php"
    }
  ]
}
---

# Personal settings

Own profile, preferences, username and password inputs, together with token metadata and derived token suffixes.
