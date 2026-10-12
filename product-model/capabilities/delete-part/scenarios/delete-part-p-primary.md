---
{
  "kind": "primary",
  "routes": {
    "route": "Public Web"
  },
  "steps": [
    {
      "text": "The caller selects the existing component for removal with valid confirmation or reference input.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
        }
      }
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
        "route": {
          "place": "web::public::public-part"
        }
      }
    },
    {
      "text": "The Product removes the selected Part and its dependent Part lots, Parameters, Order details, Price details, Associations and Attachments.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part",
          "effect": "removes"
        },
        {
          "entity": "part-lot",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "parameter",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "order-detail",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "part-association",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "attachment",
          "effect": "removes",
          "with": "part"
        },
        {
          "entity": "price-detail",
          "effect": "removes",
          "with": "order-detail"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::public-part"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartTraits/OrderTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartTraits/InstockTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartTraits/AssociationTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Orderdetail.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/PriceInformations/Pricedetail.php"
    }
  ]
}
---

# Delete part — Public Web primary

## Trigger

The caller selects the existing component for removal with valid confirmation or reference input.

## Outcome

Selected Part removed
