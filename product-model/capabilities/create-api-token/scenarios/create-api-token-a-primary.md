---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller supplies a nonempty token name, supported permission level and valid expiry.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::api-token-creation"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::api-token-creation"
        }
      }
    },
    {
      "text": "The Product creates the User-owned API token with its generated secret and reveals that secret in the creation result.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "api-token",
          "effect": "creates",
          "facts": [
            "Name",
            "Permission level",
            "Expires at",
            "Last used at",
            "Added at",
            "Secret"
          ]
        },
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Username"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::api-token-creation"
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
    }
  ]
}
---

# Create api token — Authenticated Web primary

## Trigger

The caller supplies a nonempty token name, supported permission level and valid expiry.

## Outcome

The own credential is saved and its raw secret is disclosed by this creation flow; ordinary metadata does not reveal it.
