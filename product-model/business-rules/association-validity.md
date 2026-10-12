---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part-association"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartAssociation.php"
    }
  ]
}
---

# Associations are unique directed non-self references

Association uniqueness uses its ordered originating/other/type tuple. A Part cannot associate with itself and a custom association type requires its description.
