---
{
  "kind": "edge",
  "routes": {
    "route": "MCP"
  },
  "steps": [
    {
      "text": "The caller requests matching information when the selected query or subject has no matching results.",
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
      "text": "The Product consults the separately addressed provider activity configuration for the selected provider path.",
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
      "text": "The Product returns the contract’s empty result without claiming a found inventory instance was read.",
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

# Browse provider parts — MCP empty result

## Trigger

The relevant selection has no matching result.

## Outcome

No matching external search results are returned.
