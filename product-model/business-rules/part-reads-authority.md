---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part",
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
      "target": "src/Security/Voter/PartVoter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/GetPartByIdProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/SearchPartsProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/KiCadApiController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/LabelGenerationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/LabelSystem/BarcodeScanner/BarcodeScanResultHandler.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may read Part information

Independent collection/detail browsing and export require parts.read. Explicit MCP detail checks and metadata-dependent collection checks remain distinct; declared metadata is not proof of pipeline enforcement. Label-target disclosure additionally requires labels.create_labels and its concrete target read check. KiCad category-content enumeration requires categories.read as well as parts.read; direct detail has its own Part read check and does not receive the extra category guard. Returning the accepted mutation or stock-tool result and consulting stock totals inside helper logging do not add a separate Part-read check. Scanner resolution reads found records without adding a parent-read check inside the resolver; the destination has its own check.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
