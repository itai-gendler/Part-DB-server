---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web",
    "a": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits valid new-record information with a unique name or supported parent reference.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-label-profile"
        },
        "a": {
          "place": "web::authenticated::authenticated-label-profile"
        }
      },
      "capability": "create-label-profile"
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
        "p": {
          "place": "web::public::public-label-profile"
        },
        "a": {
          "place": "web::authenticated::authenticated-label-profile"
        }
      },
      "capability": "create-label-profile"
    },
    {
      "text": "The Product saves the new Label profile with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "label-profile",
          "effect": "creates",
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
        "p": {
          "place": "web::public::public-label-profile"
        },
        "a": {
          "place": "web::authenticated::authenticated-label-profile"
        }
      },
      "capability": "create-label-profile"
    },
    {
      "text": "The Product carries the caller into the saved record’s editor.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-label-profile"
        },
        "a": {
          "place": "web::authenticated::authenticated-label-profile"
        }
      },
      "capability": "create-label-profile"
    },
    {
      "text": "The caller supplies valid changes to the selected record’s supported information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-label-profile"
        },
        "a": {
          "place": "web::authenticated::authenticated-label-profile"
        }
      },
      "capability": "edit-label-profile"
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
        "p": {
          "place": "web::public::public-label-profile"
        },
        "a": {
          "place": "web::authenticated::authenticated-label-profile"
        }
      },
      "capability": "edit-label-profile"
    },
    {
      "text": "The Product saves the supplied Label profile information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "label-profile",
          "effect": "changes",
          "facts": [
            "Name",
            "Comment",
            "Options",
            "Show in dropdown",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-label-profile"
        },
        "a": {
          "place": "web::authenticated::authenticated-label-profile"
        }
      },
      "capability": "edit-label-profile"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Create label profile and edit achieved

## Trigger

The same caller follows the source-carried continuation: Standalone Create Profile → Edit saved Profile.

## Outcome

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
