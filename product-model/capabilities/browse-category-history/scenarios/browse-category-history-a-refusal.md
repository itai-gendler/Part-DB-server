---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests browse classification record history through this contract.",
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
      "text": "The Product stops the requested browse classification history operation at its actual refusal boundary.",
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
      "target": "src/Entity/LogSystem/AbstractLogEntry.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/LogController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/LogSystem/TimeTravel.php"
    }
  ]
}
---

# Browse category history — Authenticated Web refusal

## Trigger

The caller requests browse category history and reaches its closed entry or disabled-control result.

## Outcome

The requested browse category history result is withheld; no accepted change or removal of the requested subject is produced.
