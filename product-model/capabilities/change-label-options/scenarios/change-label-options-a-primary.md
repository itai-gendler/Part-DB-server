---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller prepares valid transient label overrides from an existing saved option set.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-label-generation"
        }
      }
    },
    {
      "text": "The Product consults the User permission configuration to determine the available option controls.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-label-generation"
        }
      }
    },
    {
      "text": "The Product reads supplied saved options and prepares the accepted transient overrides.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "label-profile",
          "effect": "reads",
          "facts": [
            "Options"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-label-generation"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/LabelSystem/LabelProfile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/LabelProfileController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Change label options — Authenticated Web primary

## Trigger

The caller prepares valid transient label overrides from an existing saved option set.

## Outcome

The prepared options can be used for generation; this operation alone changes no saved Profile.

## Edge cases

- Without a supplied profile the options are transient; Group overrides are consulted only when the account setting is inherited.
