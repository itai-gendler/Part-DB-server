---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller selects a saved option set and a valid nonempty range of existing targets.",
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
          "place": "web::authenticated::authenticated-label-generation"
        }
      }
    },
    {
      "text": "The Product reads the supplied Label profile options and resolves the found target records.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "label-profile",
          "effect": "reads",
          "facts": [
            "Options"
          ]
        },
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Internal part number",
            "Stock summary"
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
      "text": "The Product returns the generated PDF for those found targets.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Generate labels — Authenticated Web primary

## Trigger

The caller selects a saved option set and a valid nonempty range of existing targets.

## Outcome

The caller receives the generated PDF for the found target set.

## Edge cases

- Profile-free Web generation uses transient new options; lot and location target branches read their corresponding retained records.
- REST can override the target type without reproducing Web option-edit controls; a supplied Twig profile is not universally prohibited.
