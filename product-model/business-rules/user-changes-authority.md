---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user",
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
      "target": "src/Controller/UserSettingsController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/SecurityController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserSystem/PasswordResetManager.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Security/Voter/UserVoter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/UserSettingsType.php"
    }
  ]
}
---

# Only callers admitted by the resolved account configuration may change User information

Own password change requires full authentication, uses the current User and the demo/SAML disabled-control boundary, without a separate self.change_password permission bit; the old password is validation rather than a grant. It changes the credential and clears Password change required. Own Username changes require the source self/users edit_username decision and demo/SAML restrictions; own profile uses self/users edit_infos and demo restrictions. The User voter admits a granted valid self operation for the matching current User; otherwise it checks the corresponding valid users operation, rather than requiring both bits. Own Preferences require full authentication and use the current User and demo restrictions without a separate invented self-settings bit. Email recovery is available only under the source ALLOW_EMAIL_PW_RESET deployment gate. Its valid redemption and request branches update credential/recovery data without inventing a kept authentication/configuration flag. Recovery does not clear Password change required; CAPTCHA, verifier, expiry, signed-in workflow rejection and password constraints are validation.

## Rationale

Authority is supplied by the resolved User’s stored Permission overrides and the consulted Group chain. Explicit User values win; unresolved inheritance is denied. An authenticated token already carrying a disabled User is refused before permission lookup. Anonymous Web requests resolve the reserved anonymous User identity. PAT and OAuth role/scope ceilings are applied before inherited permission resolution and cannot enlarge User authority. REST and KiCad require authenticated api.access_api; MCP requires authenticated api.use_mcp and endpoint enablement, with editing enablement on the explicit write processors. The initiating API client, AI agent or KiCad client remains the caller; its authenticated User supplies authority rather than a fictitious stored caller registry.
