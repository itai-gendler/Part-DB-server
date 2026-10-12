---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests browse maker record history through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-manufacturer"
        }
      }
    },
    {
      "text": "The Product stops the requested browse maker record history operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-manufacturer"
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

# Browse manufacturer history — Public Web refusal

## Trigger

The caller requests browse manufacturer history and reaches its closed entry or disabled-control result.

## Outcome

The requested browse manufacturer history result is withheld; no accepted change or removal of the requested subject is produced.
