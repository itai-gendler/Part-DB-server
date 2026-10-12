---
{
  "type": "api",
  "actors": [
    "kicad-client"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/KiCadApiController.php"
    }
  ]
}
---

# KiCad library

External EDA software discovers a component library, browses categories and their Parts, and retrieves the selected Part projection. Discovery and category enumeration belong to this contract.
