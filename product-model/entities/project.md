---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/ProjectSystem/Project.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/AbstractStructuralDBElement.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/AdminPages/BaseEntityAdminForm.php"
    }
  ],
  "domain": "projects",
  "relations": [
    {
      "entity": "project",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "bom-entry",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "part",
      "verb": "produces",
      "cardinality": "one-to-one"
    },
    {
      "entity": "parameter",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "attachment",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Project

A hierarchical project with a bill of materials and optional build Part. Its editable Status vocabulary does not establish a mandatory lifecycle sequence.

## Information kept

- **Name** — The Project name.
- **Description** — The Project description.
- **Comment** — The Project comment.
- **Order quantity** — The Project’s order quantity.
- **Status** — The nullable value draft, planning, in_production, finished or archived.
- **Order only missing Parts** — Whether ordering is limited to missing Parts.
- **Parent assignment** — The optional parent Project.
- **Build Part assignment** — The optional Part produced by building this Project.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
- **Not selectable** — Whether this Project is excluded from ordinary structural selections.
- **Alternative names** — Additional names used for structural matching.
- **Preview attachment** — The selected preview from the Project’s attachments.
