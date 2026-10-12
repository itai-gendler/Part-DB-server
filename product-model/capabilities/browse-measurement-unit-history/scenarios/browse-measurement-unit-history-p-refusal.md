---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests browse quantity unit history through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-measurement-unit"
        }
      }
    },
    {
      "text": "The Product stops the requested browse quantity unit history operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-measurement-unit"
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

# Browse measurement unit history — Public Web refusal

## Trigger

The caller requests browse measurement unit history and reaches its closed entry or disabled-control result.

## Outcome

The requested browse measurement unit history result is withheld; no accepted change or removal of the requested subject is produced.
