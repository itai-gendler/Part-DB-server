---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "add-stock",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "capability",
      "id": "withdraw-stock",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "capability",
      "id": "stocktake-part-lot",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "capability",
      "id": "move-stock",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Adjustment timestamps more than twenty minutes ahead fail

A timestamp more than twenty minutes ahead fails. Web stocktaking calls the helper before its timestamp check and normal flush; MCP checks before mutation. Web add/withdraw/move check the timestamp before invoking their helper. Parsing and helper RuntimeException failures do not all acquire the MCP expected-error envelope.
