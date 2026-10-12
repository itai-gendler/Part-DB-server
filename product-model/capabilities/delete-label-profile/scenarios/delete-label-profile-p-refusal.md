---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller requests delete saved label option set through this contract.",
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
      "text": "The Product stops the requested delete saved option set operation at its actual refusal boundary.",
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

# Delete label profile — Public Web refusal

## Trigger

The caller requests delete label profile and reaches its closed entry or disabled-control result.

## Outcome

The requested delete label profile result is withheld; no accepted change or removal of the requested subject is produced.
