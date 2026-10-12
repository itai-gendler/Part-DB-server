---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-part",
      "contexts": [
        {
          "place": "mcp"
        }
      ]
    },
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

# MCP omission preserves collections while supplied collections reconcile belonging members

Omitted supported MCP fields or collections preserve the existing values. Supplied member lists reconcile only belonging identities; omitted members in a supplied list and explicitly empty lists can remove records. A returned updated Part does not imply a separate read check.
