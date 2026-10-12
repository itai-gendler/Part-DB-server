---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user",
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
      "target": "src/Security/Voter/UserVoter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/LabelSystem/LabelDialogType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/LabelOptionsType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/ScanController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/InfoProviderController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserSystem/PasswordResetManager.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may read User information

Internal Disabled and Permission overrides evaluation is available whenever that lookup is actually reached, including when its result refuses an operation. It is not disclosure and adds no users.read or self.show_permissions prerequisite; a ceiling or earlier refusal need not consult an override. For Web label work, labels.create_labels governs generator entry, labels.edit_options governs transient override controls and labels.use_twig governs the processing-mode control. A supplied Twig-mode profile additionally disables the Options control without use_twig; generating from saved Twig options is not universally prohibited. REST generation does not reproduce every Web editing control. Web provider discovery/search and assisted preparation use info_providers.create_parts. Declared REST provider checks and MCP metadata checks remain distinguished from actual explicit processor enforcement. Provider/default settings are consulted only on reached paths. The scanner dialog uses tools.label_scanner. Generated-QR redirection lacks that explicit check, resolution does not invent an attached-parent read check, and destination pages retain their own authority. User administration reads require full authentication and the actual User/self read decision: a valid self operation can allow access to that own record, otherwise the users operation applies. The separate info attribute allows non-anonymous account information; anonymous info falls back to read. Permission-override disclosure has its own source show_permissions check, unlike internal evaluation. Credential verification and email-link preparation consult their reached own-account facts under the local sign-in or enabled-recovery flow, without a users.read requirement.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
