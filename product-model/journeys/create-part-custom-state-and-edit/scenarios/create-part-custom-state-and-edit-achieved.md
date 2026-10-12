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
          "place": "web::public::public-part-custom-state"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-custom-state"
        }
      },
      "capability": "create-part-custom-state"
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
          "place": "web::public::public-part-custom-state"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-custom-state"
        }
      },
      "capability": "create-part-custom-state"
    },
    {
      "text": "The Product saves the new Part custom state with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-custom-state",
          "effect": "creates",
          "facts": [
            "Name",
            "Comment",
            "Not selectable",
            "Alternative names",
            "Preview attachment",
            "Added at",
            "Modified at",
            "Color designation",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part-custom-state"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-custom-state"
        }
      },
      "capability": "create-part-custom-state"
    },
    {
      "text": "The Product carries the caller into the saved record’s editor.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part-custom-state"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-custom-state"
        }
      },
      "capability": "create-part-custom-state"
    },
    {
      "text": "The caller supplies valid changes to the selected record’s supported information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part-custom-state"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-custom-state"
        }
      },
      "capability": "edit-part-custom-state"
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
          "place": "web::public::public-part-custom-state"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-custom-state"
        }
      },
      "capability": "edit-part-custom-state"
    },
    {
      "text": "The Product saves the supplied Part custom state information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part-custom-state",
          "effect": "changes",
          "facts": [
            "Name",
            "Comment",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part-custom-state"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-custom-state"
        }
      },
      "capability": "edit-part-custom-state"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartCustomState.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/PartCustomStateController.php"
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

# Create part custom state and edit achieved

## Trigger

The same caller follows the source-carried continuation: Create custom State → Edit saved State.

## Outcome

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
