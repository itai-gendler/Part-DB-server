---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/ProjectSystem/ProjectBOMEntry.php"
    }
  ],
  "domain": "projects"
}
---

# BOM entry

One Project requirement, referring either to a known Part or to a free-text component.

## Information kept

- **Name** — The entry’s component name.
- **Comment** — The entry comment.
- **Quantity** — The required component quantity.
- **Mount names** — The mounting or reference names.
- **Price** — The optional manually specified price for a free-text entry.
- **Project assignment** — The owning Project.
- **Part assignment** — The optional known Part.
- **Price Currency assignment** — The optional Currency for a manually specified price.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
