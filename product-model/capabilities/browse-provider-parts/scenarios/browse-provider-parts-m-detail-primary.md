---
{
  "kind": "primary",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller supplies an active provider key and existing external reference.",
      "kind": "actor",
      "actor": "ai-agent",
      "entities": [],
      "contexts": {
        "route": {
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "ai-agent",
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
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product consults provider activity configuration.",
      "kind": "product",
      "actor": "ai-agent",
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
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product returns the external detail information without creating a kept external record.",
      "kind": "product",
      "actor": "ai-agent",
      "entities": [],
      "contexts": {
        "route": {
          "place": "mcp"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/ListInfoProvidersProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/SearchInfoProvidersProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/GetInfoProviderPartDetailsProcessor.php"
    }
  ]
}
---

# Browse provider parts — MCP detail primary

## Trigger

An external reference is selected through the provider detail contract.

## Outcome

External detail information is returned; the returned DTO is not an Entity the Product keeps.
