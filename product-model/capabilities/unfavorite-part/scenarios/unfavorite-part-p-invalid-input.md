---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part-list"
        }
      }
    },
    {
      "text": "The Product does not complete unfavorite component because the selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part-list"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Unfavorite part — Public Web invalid input

## Trigger

The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.

## Outcome

The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted. No successful unfavorite part result is asserted.
