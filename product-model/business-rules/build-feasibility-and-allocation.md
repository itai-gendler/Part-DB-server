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

# Displayed build feasibility and default allocation use distinct totals

Displayed feasibility and default allocation use different stock paths, so default allocation may include expired known lots despite expiration-sensitive displayed totals. An empty BOM maximum is zero; displaying feasibility alone is not a successful build.
