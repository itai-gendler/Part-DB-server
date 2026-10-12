---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-currency"
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
          "place": "web::authenticated::authenticated-currency"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Currency.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/CurrencyController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ]
}
---

# Delete currency — Authenticated Web invalid input

## Trigger

The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed.

## Outcome

The selected reference is absent or the required Web confirmation is invalid; no accepted removal is performed. No successful delete currency result is asserted.
