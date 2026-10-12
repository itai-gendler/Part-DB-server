---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-parts",
      "contexts": [
        {
          "place": "kicad-library"
        }
      ]
    },
    {
      "type": "capability",
      "id": "browse-categories",
      "contexts": [
        {
          "place": "kicad-library"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/EDA/KiCadHelper.php"
    }
  ]
}
---

# KiCad enumeration and direct detail retain their distinct projections

KiCad projection follows source EDA visibility/inheritance, parameter and purchasing visibility and projected stock fields. Enumeration omission does not establish direct-detail refusal. Cached quantities carry no universal immediate-freshness guarantee; negative configured depth returns the synthetic Part-DB category.
