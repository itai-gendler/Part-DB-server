---
{
  "entities": [
    {
      "entity": "project",
      "shows": [
        "Name",
        "Status",
        "Build Part assignment"
      ]
    },
    {
      "entity": "bom-entry",
      "shows": [
        "Name",
        "Quantity",
        "Mount names",
        "Part assignment"
      ]
    },
    {
      "entity": "part",
      "shows": [
        "Name",
        "Unit assignment",
        "Stock summary"
      ]
    },
    {
      "entity": "part-lot",
      "shows": [
        "Description",
        "Amount",
        "Location assignment"
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
      "target": "templates/projects/build/build.html.twig"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/projects/build/_form.html.twig"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/components/projects.macro.html.twig"
    }
  ]
}
---

# Authenticated project build

Build requirements, quantities, lot conditions, allocations and feasibility; quantity, allocation, check-choice, output-lot selection and comment inputs.
