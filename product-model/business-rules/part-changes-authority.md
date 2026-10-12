---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part",
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
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/Parts/PartsTableActionHandler.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Security/Voter/PartVoter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartMutationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parameters/AbstractParameter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Attachments/Attachment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Pricedetail.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may change Part information

Ordinary form, table, REST and MCP changes require parts.edit. Web Favorite/Unfavorite additionally require parts.change_favorite and the enclosing/table edit check. REST and MCP Favorite writes retain their generic enclosing mutation checks rather than acquiring that Web extra bit. Needs review changes use the enclosing parts.edit check. Provider-assisted updates require info_providers.create_parts together with Part edit. Merge target changes require the target-edit path and source removal retains its deletion authority. Supported nested collection reconciliation follows the enclosing mutation guard; it does not uniformly invoke every standalone child voter.
 Source-maintained containing-record modification dates follow the accepted child creation or update decision, including concrete standalone create guards; they add no independent parent edit permission.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
