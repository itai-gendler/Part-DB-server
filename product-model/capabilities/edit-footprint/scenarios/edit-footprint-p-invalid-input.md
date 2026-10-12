---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The submitted sibling name or hierarchy violates the declared constraints.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-footprint"
        }
      }
    },
    {
      "text": "The Product retains the form’s validation errors for the submitted sibling name or hierarchy violates the declared constraints. The submitted write is not accepted.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-footprint"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Footprint.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/FootprintController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Edit footprint — Public Web invalid input

## Trigger

The submitted sibling name or hierarchy violates the declared constraints.

## Outcome

The submitted sibling name or hierarchy violates the declared constraints. No successful edit footprint result is asserted.
