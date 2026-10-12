---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The supplied file or field mapping cannot be accepted; reached clearing is not assumed to roll back.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-bom-import"
        }
      }
    },
    {
      "text": "The Product does not complete import bom because the supplied file or field mapping cannot be accepted; reached clearing is not assumed to roll back.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-bom-import"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/ProjectSystem/ProjectBOMEntry.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/ProjectController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/ProjectSystem/ProjectBuildHelper.php"
    }
  ]
}
---

# Import bom — Public Web invalid input

## Trigger

The supplied file or field mapping cannot be accepted; reached clearing is not assumed to roll back.

## Outcome

The supplied file or field mapping cannot be accepted; reached clearing is not assumed to roll back. No successful import bom result is asserted.
