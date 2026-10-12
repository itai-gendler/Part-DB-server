---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part-custom-state",
      "effect": "removes"
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
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/DeleteStructuralElementProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Security/Voter/StructureVoter.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may remove Part custom state information

Selected removal requires part_custom_states.delete. Explicit Web deletion checks and child handling are retained; MCP does not offer deletion of this type; REST resource deletion does not acquire their tree-operation parity. Dependent records removed with their holder follow the holder’s accepted removal.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
