---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web",
    "a": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits valid new-record information with a unique name or supported parent reference.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-currency"
        },
        "a": {
          "place": "web::authenticated::authenticated-currency"
        }
      },
      "capability": "create-currency"
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-currency"
        },
        "a": {
          "place": "web::authenticated::authenticated-currency"
        }
      },
      "capability": "create-currency"
    },
    {
      "text": "The Product saves the new Currency with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "currency",
          "effect": "creates",
          "facts": [
            "Name",
            "Comment",
            "Not selectable",
            "Alternative names",
            "Preview attachment",
            "Added at",
            "Modified at",
            "ISO code",
            "Exchange rate",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-currency"
        },
        "a": {
          "place": "web::authenticated::authenticated-currency"
        }
      },
      "capability": "create-currency"
    },
    {
      "text": "The Product carries the caller into the saved record’s editor.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-currency"
        },
        "a": {
          "place": "web::authenticated::authenticated-currency"
        }
      },
      "capability": "create-currency"
    },
    {
      "text": "The caller supplies valid changes to the selected record’s supported information.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-currency"
        },
        "a": {
          "place": "web::authenticated::authenticated-currency"
        }
      },
      "capability": "edit-currency"
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-currency"
        },
        "a": {
          "place": "web::authenticated::authenticated-currency"
        }
      },
      "capability": "edit-currency"
    },
    {
      "text": "The Product saves the supplied Currency information through the implemented write.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "currency",
          "effect": "changes",
          "facts": [
            "Name",
            "Comment",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-currency"
        },
        "a": {
          "place": "web::authenticated::authenticated-currency"
        }
      },
      "capability": "edit-currency"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Create currency and edit achieved

## Trigger

The same caller follows the source-carried continuation: Create Currency → Edit saved Currency.

## Outcome

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
