---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The submitted sibling name or hierarchy violates the declared constraints.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-category"
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
          "place": "web::authenticated::authenticated-category"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Category.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/CategoryController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Edit category — Authenticated Web invalid input

## Trigger

The submitted sibling name or hierarchy violates the declared constraints.

## Outcome

The submitted sibling name or hierarchy violates the declared constraints. No successful edit category result is asserted.
