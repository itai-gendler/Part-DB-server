---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part-lot",
      "effect": "changes"
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
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/Part/PartLotType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartLotStockProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartMutationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/ProjectController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/ProjectSystem/ProjectBuildHelper.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may change Part lot information

Ordinary metadata and direct Amount changes follow the actual enclosing/resource Part-edit guard without an adjustment-specific owner restriction. PATCH’s pre-denormalization check does not promise an additional check on a newly supplied parent. Direct Last stocktake on Web needs enclosing edit and parts_stock.stocktake for its field control. REST’s direct writable field retains the concrete edit check without that extra Web bit; MCP has no corresponding existing-lot date input. Addition requires parts_stock.add; withdrawal requires parts_stock.withdraw; absolute stocktaking requires parts_stock.stocktake. Each adjustment additionally requires that an owned lot’s Owner equals the resolved User by object or ID; an unowned lot needs only the operation’s permission. Movement checks parts_stock.move and that same owner condition separately for source and an existing target. A new target instead follows its concrete creation check and metadata validation, without inventing an existing-target move-owner check. Project-build allocation changes require Project read and global parts_stock.withdraw. The handler has no per-lot owner voter; disabled owner-sensitive controls do not establish one. Its output helper addition follows accepted build authority without an additional parts_stock.add/owner check, while actual helper eligibility still applies. MCP adjustment processors check editing enablement before resolving the lot and perform the explicit requested-operation voter. Nested MCP metadata edits use enclosing Part edit; supplying existing-lot Amount is rejected rather than treated as direct editing.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
