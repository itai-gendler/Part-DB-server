---
{
  "kind": "validation",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product does not remove the requested record when its confirmation or reference is invalid.",
      "kind": "product",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartCustomState.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/PartCustomStateController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Delete part custom state — REST invalid input

## Trigger

The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed.

## Outcome

The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed. No successful delete part custom state result is asserted.
