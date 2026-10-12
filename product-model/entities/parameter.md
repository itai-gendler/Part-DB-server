---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parameters/AbstractParameter.php"
    }
  ]
}
---

# Parameter

A named value or value range attached to a supported subject. The same information list applies to all twelve supported subject classes.

## Information kept

- **Name** — The parameter name.
- **Group** — The parameter group.
- **Symbol** — The parameter symbol.
- **Unit** — The parameter’s textual unit.
- **Text value** — The text value.
- **Minimum value** — The optional minimum numeric value.
- **Typical value** — The optional typical numeric value.
- **Maximum value** — The optional maximum numeric value.
- **EDA visibility** — Whether this parameter is exposed to EDA consumers.
- **EDA symbol visibility** — Whether the parameter is visible on the EDA symbol.
- **Subject assignment** — The supported subject to which this Parameter belongs.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
