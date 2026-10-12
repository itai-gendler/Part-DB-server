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
          "place": "web::public::public-measurement-unit"
        },
        "a": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      },
      "capability": "create-measurement-unit"
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
          "place": "web::public::public-measurement-unit"
        },
        "a": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      },
      "capability": "create-measurement-unit"
    },
    {
      "text": "The Product saves the new Measurement unit with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "measurement-unit",
          "effect": "creates",
          "facts": [
            "Name",
            "Comment",
            "Not selectable",
            "Alternative names",
            "Preview attachment",
            "Added at",
            "Modified at",
            "Unit symbol",
            "Integer amounts",
            "SI prefixes",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-measurement-unit"
        },
        "a": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      },
      "capability": "create-measurement-unit"
    },
    {
      "text": "The Product carries the caller into the saved record’s editor.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-measurement-unit"
        },
        "a": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      },
      "capability": "create-measurement-unit"
    },
    {
      "text": "The caller supplies valid changes to the selected record’s supported information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-measurement-unit"
        },
        "a": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      },
      "capability": "edit-measurement-unit"
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
          "place": "web::public::public-measurement-unit"
        },
        "a": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      },
      "capability": "edit-measurement-unit"
    },
    {
      "text": "The Product saves the supplied Measurement unit information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "measurement-unit",
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
          "place": "web::public::public-measurement-unit"
        },
        "a": {
          "place": "web::authenticated::authenticated-measurement-unit"
        }
      },
      "capability": "edit-measurement-unit"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/MeasurementUnit.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/MeasurementUnitController.php"
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

# Create measurement unit and edit achieved

## Trigger

The same caller follows the source-carried continuation: Create Unit → Edit saved Unit.

## Outcome

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
