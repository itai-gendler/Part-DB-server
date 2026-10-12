---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller requests token metadata from the personal-account contract.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product discloses matching API token information through this contract.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "api-token",
          "effect": "reads",
          "facts": [
            "Name",
            "Permission level",
            "Expires at",
            "Last used at",
            "Added at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/UserSystem/ApiToken.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/UserSettingsController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/UserController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/GroupController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/CurrentApiTokenProvider.php"
    }
  ]
}
---

# Browse api tokens — REST primary

## Trigger

The caller requests token metadata from the personal-account contract.

## Outcome

Own token metadata is shown on Web; REST returns the current authenticated API-token object without revealing its full secret.
