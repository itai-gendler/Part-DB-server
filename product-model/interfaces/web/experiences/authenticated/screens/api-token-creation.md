---
{
  "entities": [
    {
      "entity": "api-token",
      "collects": [
        "Name",
        "Permission level",
        "Expires at"
      ],
      "shows": [
        "Name",
        "Permission level",
        "Expires at",
        "Last used at",
        "Added at",
        "Secret"
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

# API token creation

Token name, level and expiry input; successful credential creation reveals its secret here.
