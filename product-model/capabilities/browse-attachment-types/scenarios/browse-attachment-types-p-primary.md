---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller opens the collection and selects from the available record identities.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-attachment-type"
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
          "place": "web::public::public-attachment-type"
        }
      }
    },
    {
      "text": "The Product returns the available Attachment type identities and names in their parent/child grouping.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment-type",
          "effect": "reads",
          "facts": [
            "Name",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-attachment-type"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Attachments/AttachmentType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/AttachmentTypeController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/Trees/TreeViewGenerator.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Repository/StructuralDBElementRepository.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/admin/base_admin.html.twig"
    }
  ]
}
---

# Browse attachment types — Public Web primary

## Trigger

The caller opens the collection and selects from the available record identities.

## Outcome

The collection discloses the available identities and names; a selected record has its separate detail case.
