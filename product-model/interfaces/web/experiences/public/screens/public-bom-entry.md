---
{
  "entities": [
    {
      "entity": "project",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "bom-entry",
      "shows": [
        "Name",
        "Comment",
        "Quantity",
        "Mount names",
        "Price",
        "Part assignment",
        "Price Currency assignment"
      ],
      "collects": [
        "Name",
        "Comment",
        "Quantity",
        "Mount names",
        "Price",
        "Part assignment",
        "Price Currency assignment"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/ProjectController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/projects/edit_bom_entry.html.twig"
    }
  ]
}
---

# Public bom entry

The selected requirement, comments, component references and pricing; supported name, quantity, mount names and free-text price inputs.
