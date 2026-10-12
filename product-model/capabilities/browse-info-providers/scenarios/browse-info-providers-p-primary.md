---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests the available provider descriptions.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-info-provider-search"
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
          "place": "web::public::public-info-provider-search"
        }
      }
    },
    {
      "text": "The Product consults the separately addressed provider activity configuration for the selected provider path.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "product-settings",
          "effect": "reads",
          "facts": [
            "Provider activity configuration"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-info-provider-search"
        }
      }
    },
    {
      "text": "The Product returns provider descriptions.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-info-provider-search"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Settings/AppSettings.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/InfoProviderController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/InfoProviderSystem/ProviderRegistry.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/InfoProviderSystem/Providers/MouserProvider.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/InfoProviderSystem/DTOs/ProviderInfoDTO.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/InfoProviderSystem/DTOs/SearchResultDTO.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/InfoProviderSystem/DTOs/PartDetailDTO.php"
    }
  ]
}
---

# Browse info providers — Public Web primary

## Trigger

The caller requests the available provider descriptions.

## Outcome

Available provider descriptions disclosed
