---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Settings/AppSettings.php"
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
      "target": "src/Settings/InfoProviderSystem/MouserSettings.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Settings/InfoProviderSystem/InfoProviderSettings.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "config/packages/settings.yaml"
    }
  ],
  "domain": "system-settings",
  "singleton": true
}
---

# Product settings

The Product’s configuration, including the six general sections and separately addressed provider activity inputs. Source-declared environment overrides take precedence for applicable settings.

## Information kept

- **System options** — The saved system-section options.
- **Behavior options** — The saved behavior-section options.
- **Information-provider options** — The saved provider-section options.
- **Synonym options** — The saved entity-synonym options.
- **AI options** — The saved AI-section options.
- **Miscellaneous options** — The saved miscellaneous-section options.
- **MCP enabled** — Whether the MCP endpoint is enabled.
- **MCP editing enabled** — Whether MCP editing is enabled.
- **Provider activity configuration** — Separately addressed saved provider switches and credentials consulted by registry activity checks; these are not embedded in the general Information-provider options. Mouser activity, for example, depends on its configured API key.
