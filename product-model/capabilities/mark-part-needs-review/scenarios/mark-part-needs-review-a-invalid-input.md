---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part-list"
        }
      }
    },
    {
      "text": "The Product does not complete mark component needs review because the selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part-list"
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

# Mark part needs review — Authenticated Web invalid input

## Trigger

The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted.

## Outcome

The selected reference or enclosing mutation input is invalid; the requested flag change is not accepted. No successful mark part needs review result is asserted.
