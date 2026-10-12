---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests the supported information of one existing selected record.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-label-profile"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
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
          "place": "web::authenticated::authenticated-label-profile"
        }
      }
    },
    {
      "text": "The Product discloses the selected Label profile information through this contract.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "label-profile",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
            "Options",
            "Show in dropdown",
            "Preview attachment",
            "Added at",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-label-profile"
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

# Browse label profiles — Authenticated Web detail primary

## Trigger

One existing subject is selected for its detail information.

## Outcome

Profiles disclosed
