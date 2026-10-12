---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "category"
    },
    {
      "type": "entity",
      "id": "footprint"
    },
    {
      "type": "entity",
      "id": "storage-location"
    },
    {
      "type": "entity",
      "id": "supplier"
    },
    {
      "type": "entity",
      "id": "manufacturer"
    },
    {
      "type": "entity",
      "id": "currency"
    },
    {
      "type": "entity",
      "id": "measurement-unit"
    },
    {
      "type": "entity",
      "id": "part-custom-state"
    },
    {
      "type": "entity",
      "id": "attachment-type"
    },
    {
      "type": "entity",
      "id": "project"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/AbstractStructuralDBElement.php"
    }
  ]
}
---

# Structural records satisfy sibling and hierarchy constraints

The structural sibling-name and hierarchy constraints apply to the nine structural types and Projects. Currency ISO validity/uniqueness, unit symbol/SI configuration and the specialized Location constraints remain applicable.
