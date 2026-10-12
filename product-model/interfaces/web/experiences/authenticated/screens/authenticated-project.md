---
{
  "entities": [
    {
      "entity": "project",
      "shows": [
        "Name",
        "Description",
        "Comment",
        "Status",
        "Parent assignment",
        "Build Part assignment",
        "Added at",
        "Modified at",
        "Not selectable",
        "Alternative names",
        "Preview attachment"
      ],
      "collects": [
        "Name",
        "Description",
        "Comment",
        "Status",
        "Parent assignment",
        "Not selectable",
        "Alternative names",
        "Preview attachment"
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
        "Project assignment",
        "Part assignment",
        "Price Currency assignment",
        "Added at",
        "Modified at"
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
    },
    {
      "entity": "part",
      "shows": [
        "Name",
        "Description",
        "Internal part number",
        "Manufacturing status",
        "Category assignment",
        "Footprint assignment",
        "Manufacturer assignment",
        "Unit assignment",
        "Custom state assignment",
        "Stock summary",
        "Preview attachment"
      ]
    },
    {
      "entity": "part-lot",
      "shows": [
        "Amount",
        "Unknown amount",
        "Location assignment"
      ]
    },
    {
      "entity": "parameter",
      "shows": [
        "Name",
        "Group",
        "Symbol",
        "Unit",
        "Text value",
        "Minimum value",
        "Typical value",
        "Maximum value"
      ],
      "collects": [
        "Name",
        "Group",
        "Symbol",
        "Unit",
        "Text value",
        "Minimum value",
        "Typical value",
        "Maximum value"
      ]
    },
    {
      "entity": "attachment",
      "shows": [
        "Name",
        "Original filename",
        "External URL",
        "Show in table",
        "Type assignment"
      ],
      "collects": [
        "Name",
        "Original filename",
        "External URL",
        "Show in table",
        "Type assignment"
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
      "target": "src/Form/AdminPages/ProjectAdminForm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/ProjectSystem/ProjectBOMEntryType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/DataTables/ProjectBomEntriesDataTable.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/projects/info/info.html.twig"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/AdminPages/BaseEntityAdminForm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/ParameterType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/AttachmentFormType.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/admin/project_admin.html.twig"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "templates/admin/base_admin.html.twig"
    }
  ]
}
---

# Authenticated project

Project information, BOM entries and stock/pricing summaries; project edits and new BOM-entry inputs.
