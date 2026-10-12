---
{
  "kind": "edge",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller omits provider selections and reaches inactive, absent or invalid configured defaults.",
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
      "text": "The Product consults applicable default search selections and provider activity configuration.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "product-settings",
          "effect": "reads",
          "facts": [
            "Information-provider options",
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
      "text": "The Product encounters the selected provider or default-provider retrieval failure.",
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

# Browse provider parts — Provider/default-provider failures remain distinguished (Public Web)

## Trigger

The caller omits provider selections and reaches inactive, absent or invalid configured defaults.

## Outcome

The retrieval failure remains distinguished from successful external results; returned external DTOs are not kept records.
