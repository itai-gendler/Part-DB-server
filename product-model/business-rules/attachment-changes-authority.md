---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "attachment",
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
      "target": "src/Security/Voter/AttachmentVoter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartMutationProcessor.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may change Attachment information

Concrete metadata/create/delete mutations map to attached-subject edit. Class fallback maps the attachment subject type to its corresponding permission and checks edit for create/edit/delete, retaining the same mutation mapping as concrete subject access. The recognized class branches cover the twelve Parameter-owner types plus User; the LabelAttachment class-only fallback has no matching branch and fails as an unsupported type. Concrete Label-profile attachment mutations use the attached profile edit decision. The deleted abstract-class fallback uses parts.edit; a concrete attachment with no supported subject is refused. Nested submission follows its enclosing mutation guard; there is no mapped MCP attachment-write context. Dependent creation or removal with an authorized holder uses that holder’s decision rather than a separate child grant.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
