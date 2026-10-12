---
{
  "kind": "validation",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-footprint"
        }
      }
    },
    {
      "text": "The Product does not remove the requested record when its confirmation or reference is invalid.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-footprint"
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

# Delete footprint — Public Web invalid input

## Trigger

The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed.

## Outcome

The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed. No successful delete footprint result is asserted.
