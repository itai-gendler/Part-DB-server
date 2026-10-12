---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests generate labels through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-label-generation"
        }
      }
    },
    {
      "text": "The Product consults the User permission configuration and leaves the requested operation or control unavailable.",
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
          "place": "web::public::public-label-generation"
        }
      }
    },
    {
      "text": "The Product stops the requested generate labels operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-label-generation"
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

# Generate labels — Public Web refusal

## Trigger

The caller requests generate labels and reaches its closed entry or disabled-control result.

## Outcome

The requested generate labels result is withheld; no accepted change or removal of the requested subject is produced.
