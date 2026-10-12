---
{
  "availability": [
    {
      "place": "web::public"
    },
    {
      "place": "web::authenticated"
    },
    {
      "place": "rest-api"
    },
    {
      "place": "mcp"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/AbstractStructuralElementMutationProcessor.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/McpToolErrorHandling.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/Mcp/UpdateStructuralElementProcessor.php"
    }
  ],
  "domain": "footprints"
}
---

# Edit footprint

Supplied Footprint changes are saved.
