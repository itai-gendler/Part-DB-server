---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller requests one selected record’s details.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-footprint"
        }
      }
    },
    {
      "text": "The Product stops the selected-detail disclosure at the explicit detail-check boundary.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-footprint"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Footprint.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/FootprintController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Browse footprints — Authenticated Web detail refusal

## Trigger

The selected-detail request reaches its explicit refusal boundary.

## Outcome

The selected subject’s detail information is not disclosed by this request.
