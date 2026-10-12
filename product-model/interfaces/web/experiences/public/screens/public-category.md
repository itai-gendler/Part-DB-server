---
{
  "entities": [
    {
      "entity": "category",
      "shows": [
        "Name",
        "Comment",
        "Not selectable",
        "Alternative names",
        "Preview attachment",
        "Added at",
        "Modified at",
        "Part name hint",
        "Part name pattern",
        "Internal part number prefix",
        "Default description",
        "Default comment",
        "Disabled Part features",
        "EDA information",
        "Parent assignment"
      ],
      "collects": [
        "Name",
        "Comment",
        "Not selectable",
        "Alternative names",
        "Preview attachment",
        "Part name hint",
        "Part name pattern",
        "Internal part number prefix",
        "Default description",
        "Default comment",
        "Disabled Part features",
        "EDA information",
        "Parent assignment"
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
        "Maximum value",
        "Subject assignment",
        "Added at",
        "Modified at"
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
        "Internal file reference",
        "External URL",
        "Show in table",
        "Subject assignment",
        "Type assignment",
        "Content classification",
        "Added at",
        "Modified at"
      ],
      "collects": [
        "Name",
        "Original filename",
        "External URL",
        "Show in table",
        "Type assignment"
      ]
    },
    {
      "entity": "activity-entry",
      "shows": [
        "Actor name",
        "Occurred at",
        "Event kind",
        "Severity",
        "Access method",
        "Target reference",
        "Event details",
        "Request correlation",
        "Transaction correlation"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/CategoryController.php"
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
    }
  ]
}
---

# Public category

Category information, supported parameters and attachments and relevant history; the source-supported record and nested inputs.
