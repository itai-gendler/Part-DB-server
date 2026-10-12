---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bom-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/ProjectSystem/ProjectBOMEntry.php"
    }
  ]
}
---

# BOM requirements satisfy quantity, mounting and component constraints

A BOM entry has positive quantity and either a known Part or a Name. Integer requirements are rounded; Mount names are unique and count-matching where supplied. Manual Price is for free-text entries. The Project’s own or ancestor build Parts cannot be included.
