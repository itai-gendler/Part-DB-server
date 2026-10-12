---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The supplied range, saved-profile reference or wholly absent target set prevents label generation.",
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
      "text": "The Product fails the selected options/range/target validation and does not produce an accepted label result.",
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

# Generate labels — Public Web invalid input

## Trigger

The supplied range, saved-profile reference or wholly absent target set prevents label generation.

## Outcome

The supplied range, saved-profile reference or wholly absent target set prevents label generation. No successful generate labels result is asserted.
