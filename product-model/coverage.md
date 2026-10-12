---
{
  "scope": "Initial broad mapping of the named inventory, stock, purchasing, attachments, classifications, projects, labels, providers, account settings, permissions, history and four inbound contracts at source commit c8d3b64fd5e7bec9ebfe6425d5cc894424082db2.",
  "method": "Read-only repository inventory and static traces from browser and machine entry points through reached forms, validation, permission resolution, handlers, persistence, logging and observable outcomes; supporting templates and translations establish selected places and shipped names.",
  "covered": [
    {
      "description": "Selected inventory, structural, purchasing, shared Parameter/Attachment, Project/BOM, Profile, account, Group, token and activity information, relations and resource metadata in the named catalogue.",
      "paths": [
        "src/Entity/"
      ]
    },
    {
      "description": "Browser operations and source-carried continuations for the named catalogue, with their actual form inputs, validation boundaries and disclosure places.",
      "paths": [
        "src/Controller/",
        "src/Form/",
        "src/Validator/",
        "templates/"
      ]
    },
    {
      "description": "Selected REST processors and MCP DTO/processor contracts, distinguishing explicit checks, reconciliation, result disclosure, errors and metadata-only declarations.",
      "paths": [
        "src/State/",
        "src/Mcp/DTO/",
        "config/packages/security.yaml"
      ]
    },
    {
      "description": "User/Group permission inheritance, anonymous identity, ownership voters, authenticated-principal binding, disabled-account decisions and PAT/OAuth ceilings reached by the mapped contracts.",
      "paths": [
        "src/Security/",
        "src/Services/UserSystem/",
        "src/Entity/UserSystem/",
        "config/packages/security.yaml"
      ]
    },
    {
      "description": "Stock helper arithmetic, eligibility, rounding, cleanup, caller flush order and reached stock logging, together with actual location/lot constraints and enclosing writes.",
      "paths": [
        "src/Services/Parts/",
        "src/State/Mcp/",
        "src/Form/Part/",
        "src/Validator/Constraints/",
        "src/Entity/LogSystem/"
      ]
    },
    {
      "description": "Selected ordinary Project/BOM allocation, validation, import clearing/matching and export behavior, including existing/new output-lot build paths.",
      "paths": [
        "src/Services/ProjectSystem/",
        "src/Helpers/Projects/",
        "src/Services/ImportExportSystem/",
        "src/Controller/ProjectController.php"
      ]
    },
    {
      "description": "Provider descriptions/search/details, assisted Part preparation, local matching and reached registry activity checks; selected saved switches/keys are distinct from the general defaults section.",
      "paths": [
        "src/Services/InfoProviderSystem/",
        "src/State/Mcp/",
        "src/Settings/InfoProviderSystem/",
        "config/packages/settings.yaml"
      ]
    },
    {
      "description": "Profile options, generation, found-target selection and barcode resolution/continuations; selected KiCad category/component visibility, inheritance and cache projections.",
      "paths": [
        "src/Services/LabelSystem/",
        "src/Services/EDA/",
        "src/State/LabelGenerationProcessor.php",
        "src/Settings/MiscSettings/"
      ]
    },
    {
      "description": "Selected attachment reference/content handling, merger reconciliation, activity recording and historical disclosure, excluding persisted reversal operations.",
      "paths": [
        "src/Services/Attachments/",
        "src/Services/EntityMergers/",
        "src/Services/LogSystem/"
      ]
    },
    {
      "description": "Six general settings sections, MCP switches, reached environment precedence/cache invalidation, selected navigation exposure and shipped terminology.",
      "paths": [
        "src/Settings/",
        "src/Controller/SettingsController.php",
        "src/EventSubscriber/",
        "src/Services/Trees/",
        "templates/",
        "translations/"
      ]
    },
    {
      "description": "Inspected structural-overview normalization and selected resource serialization groups distinguish collection projections from item details and browser forms.",
      "paths": [
        "src/Serializer/",
        "src/Entity/"
      ]
    },
    {
      "description": "Base administration entry, disabled form controls and final edit checks retain their distinct authorization points; reached nested forms distinguish supplied fields from generated parent links and provider-maintained quantities.",
      "paths": [
        "src/Controller/AdminPages/",
        "src/Form/",
        "templates/admin/"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Build/deployment/package automation, migration mechanics and development/test materials serve as implementation support rather than additional Product resources.",
      "paths": [
        ".github/",
        "Dockerfile",
        "composer.json",
        "package.json",
        "migrations/",
        "tests/"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "OAuth authorization/consent, registration and connected-app administration, detailed SAML/LDAP authentication, second-factor enrollment/challenges/recovery, WebAuthn/U2F and impersonation.",
      "paths": [
        "src/Security/",
        "src/Controller/",
        "src/Entity/UserSystem/",
        "templates/security/"
      ]
    },
    {
      "description": "User/Group creation, editing, deletion, permission editing/presets, password administration and special-account protection workflows beyond the inspected reads and personal account work.",
      "paths": [
        "src/Controller/UserController.php",
        "src/Controller/GroupController.php",
        "src/Form/",
        "src/Entity/UserSystem/"
      ]
    },
    {
      "description": "Bulk provider jobs/refresh, most batch changes, generated-image and document/URL extraction workflows; the selected Favorite and Needs-review actions are mapped.",
      "paths": [
        "src/Controller/",
        "src/Services/InfoProviderSystem/",
        "src/Services/Parts/",
        "assets/"
      ]
    },
    {
      "description": "Detailed initialization and management of Project build Parts beyond the configured output reference and accepted build-output stock behavior.",
      "paths": [
        "src/Services/ProjectSystem/",
        "src/Controller/ProjectController.php"
      ]
    },
    {
      "description": "Undo, revert and undelete, including their consequential permission and restoration branches.",
      "paths": [
        "src/Services/LogSystem/",
        "src/Controller/LogController.php",
        "src/Entity/LogSystem/"
      ]
    },
    {
      "description": "Provider-specific configuration editing/OAuth, extraction policy, costs/rate limits and the complete external failure catalogue; registry activity inputs alone do not cover these workflows.",
      "paths": [
        "src/Settings/InfoProviderSystem/",
        "src/Services/InfoProviderSystem/",
        "src/Controller/InfoProviderController.php"
      ]
    },
    {
      "description": "Currency-rate updates, statistics, calculators, built-in footprint/logo tools, server information and update-management workflows.",
      "paths": [
        "src/Controller/",
        "src/Services/"
      ]
    },
    {
      "description": "Console, scheduled, maintenance and setup contracts that were not independently traced.",
      "paths": [
        "src/Command/"
      ]
    },
    {
      "description": "Detailed label formats, every vendor barcode parser and camera/device behavior beyond selected local/vendor resolution and generation boundaries.",
      "paths": [
        "src/Services/LabelSystem/",
        "assets/"
      ]
    },
    {
      "description": "Detailed MCP advanced-search operators and Part-preview transformations beyond inspected authorization leads and selected ordinary search/detail outcomes.",
      "paths": [
        "src/State/Mcp/",
        "src/Mcp/DTO/"
      ]
    },
    {
      "description": "Frontend-specific interaction behavior beyond selected entry/continuation evidence, and additional repository queries, persistence transformations and resource operations beyond the named catalogue.",
      "paths": [
        "assets/",
        "src/Repository/",
        "src/Entity/",
        "src/State/"
      ]
    }
  ],
  "limitations": [
    {
      "description": "MCP collection/provider metadata security lacks corroboration from the dependency call pipeline; source comments distinguish declared metadata from explicit processor checks.",
      "paths": [
        "src/Entity/",
        "src/State/Mcp/",
        "src/Services/InfoProviderSystem/DTOs/"
      ]
    },
    {
      "description": "Reached ORM flush, stock logging, cache and mail-preparation paths were inspected locally; dependency-level transaction, cache-completion and mail-delivery behavior was not established.",
      "paths": [
        "src/Services/Parts/",
        "src/Services/ProjectSystem/",
        "src/Services/LogSystem/",
        "src/Services/UserSystem/",
        "src/Services/EDA/",
        "src/State/Mcp/"
      ]
    }
  ]
}
---

# Coverage
