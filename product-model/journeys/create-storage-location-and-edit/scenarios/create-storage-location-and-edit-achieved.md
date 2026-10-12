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
          "place": "web::public::public-storage-location"
        },
        "a": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      },
      "capability": "create-storage-location"
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
          "place": "web::public::public-storage-location"
        },
        "a": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      },
      "capability": "create-storage-location"
    },
    {
      "text": "The Product saves the new Storage location with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-location",
          "effect": "creates",
          "facts": [
            "Name",
            "Comment",
            "Not selectable",
            "Alternative names",
            "Preview attachment",
            "Added at",
            "Modified at",
            "Full",
            "Single Part only",
            "Existing Parts only",
            "Owner must match",
            "Owner assignment",
            "Storage type",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-storage-location"
        },
        "a": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      },
      "capability": "create-storage-location"
    },
    {
      "text": "The Product carries the caller into the saved record’s editor.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-storage-location"
        },
        "a": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      },
      "capability": "create-storage-location"
    },
    {
      "text": "The caller supplies valid changes to the selected record’s supported information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-storage-location"
        },
        "a": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      },
      "capability": "edit-storage-location"
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
          "place": "web::public::public-storage-location"
        },
        "a": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      },
      "capability": "edit-storage-location"
    },
    {
      "text": "The Product saves the supplied Storage location information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "storage-location",
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
          "place": "web::public::public-storage-location"
        },
        "a": {
          "place": "web::authenticated::authenticated-storage-location"
        }
      },
      "capability": "edit-storage-location"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/StorageLocation.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/StorageLocationController.php"
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

# Create storage location and edit achieved

## Trigger

The same caller follows the source-carried continuation: Create Location → Edit saved Location.

## Outcome

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
