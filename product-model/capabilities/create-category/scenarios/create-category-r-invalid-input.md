---
{
  "kind": "validation",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The submitted sibling name or hierarchy violates the declared constraints.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product does not complete create classification record because the submitted sibling name or hierarchy violates the declared constraints.",
      "kind": "product",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
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

# Create category — REST invalid input

## Trigger

The submitted sibling name or hierarchy violates the declared constraints.

## Outcome

The submitted sibling name or hierarchy violates the declared constraints. No successful create category result is asserted.
