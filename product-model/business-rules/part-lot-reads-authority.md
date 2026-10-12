---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part-lot",
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
      "target": "src/Security/Voter/PartLotVoter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/Parts/PartLotWithdrawAddHelper.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/LabelGenerationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/ProjectController.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may read Part lot information

Internal lot identity, parent and owner consultation is available when the controller or voter reaches it, including paths that later reject an amount or refuse an adjustment; it adds no independent disclosure permission. Independent or nested lot disclosure follows the attached Part’s read decision. Label targets additionally require labels.create_labels and the concrete target read check. Stock helper eligibility, owner and quantity consultation follows the requested adjustment’s check; it does not add an independent Part-read check. MCP stock results return the updated Part without a separate detail-read voter. Build allocation/feasibility consultation follows Project read and the reached build path.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
