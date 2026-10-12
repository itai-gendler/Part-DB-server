---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests browse saved label option sets through this contract.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-label-profile"
        }
      }
    },
    {
      "text": "The Product stops the requested browse saved option set operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-label-profile"
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

# Browse label profiles — Public Web refusal

## Trigger

The caller requests browse label profiles and reaches its closed entry or disabled-control result.

## Outcome

The requested browse label profiles result is withheld; no accepted change or removal of the requested subject is produced.
