---
{
  "kind": "edge",
  "routes": {
    "route": "KiCad library"
  },
  "steps": [
    {
      "text": "The caller reads a component projection with cached stock information after a stock change.",
      "kind": "actor",
      "actor": "kicad-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "kicad-library"
        }
      }
    },
    {
      "text": "The Product reads and returns the cached Part stock projection.",
      "kind": "product",
      "actor": "kicad-client",
      "entities": [
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name",
            "Stock summary"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "kicad-library"
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
      "target": "src/Controller/KiCadApiController.php"
    }
  ]
}
---

# Browse parts — Cached stock projection carries no immediate-freshness guarantee (KiCad library)

## Trigger

The caller reads a component projection with cached stock information after a stock change.

## Outcome

The KiCad projection can reuse cached stock data; an immediately fresh quantity after every write is not guaranteed.
