---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "build-project",
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
      "target": "src/Services/ProjectSystem/ProjectBuildHelper.php"
    }
  ]
}
---

# Accepted builds withdraw allocations and handle configured output through reached flushes

Accepted positive build allocations use the withdrawal helper. Configured output uses helper addition of completed-unit quantity and its actual eligibility checks. The caller can flush a new output lot before build work and flush after; no completion counter, atomic rollback or per-lot server owner voter is promised.
