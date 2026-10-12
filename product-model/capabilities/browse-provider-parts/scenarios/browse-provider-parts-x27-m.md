---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller omits provider selections and reaches inactive, absent or invalid configured defaults.",
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
      "text": "The Product consults applicable default search selections and provider activity configuration.",
      "kind": "product",
      "actor": "ai-agent",
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
          "place": "mcp"
        }
      }
    },
    {
      "text": "The Product encounters the selected provider or default-provider retrieval failure.",
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

# Browse provider parts — Provider/default-provider failures remain distinguished (MCP)

## Trigger

The caller omits provider selections and reaches inactive, absent or invalid configured defaults.

## Outcome

The retrieval failure remains distinguished from successful external results; returned external DTOs are not kept records.
