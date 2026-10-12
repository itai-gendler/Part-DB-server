---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "product-settings",
      "effect": "reads"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserSystem/PermissionManager.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserSystem/VoterHelper.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/UserSystem/PermissionData.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "config/packages/security.yaml"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/SettingsController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/EventSubscriber/McpAccessSubscriber.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Settings/AISettings/McpSettings.php"
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
      "target": "src/Services/EDA/KiCadHelper.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may read Product settings information

Internal KiCad projection evaluation consults Miscellaneous options for depth, projection choices and defaults without adding an administration-read permission. Independent system-settings disclosure requires full authentication and config.change_system_settings. Internal configuration evaluation is not settings disclosure and adds no permission to read the evaluator’s own inputs. Reached MCP endpoint/editing checks consult their actual switches, including a disabled-switch refusal before inventory lookup. Reached provider registry checks consult separately addressed activity settings, and default searches use the general default-provider selection. This does not disclose provider secrets or cover provider-specific settings editing. Web label/scanner/provider operation decisions retain the resolved User configuration described by the operation’s policy; a failed earlier gate does not manufacture later settings reads.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
