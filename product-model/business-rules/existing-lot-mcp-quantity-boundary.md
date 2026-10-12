---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-part",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractPartMutationProcessor.php"
    }
  ]
}
---

# MCP existing-lot updates cannot supply Amount

Supplying Amount for an existing MCP lot is rejected. New-lot amount input is supported separately; ordinary existing-lot metadata is not thereby prohibited.
