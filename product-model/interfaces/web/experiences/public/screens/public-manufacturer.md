---
{
  "entities": [
    {
      "entity": "manufacturer",
      "shows": [
        "Name",
        "Comment",
        "Not selectable",
        "Alternative names",
        "Preview attachment",
        "Added at",
        "Modified at",
        "Address",
        "Phone",
        "Fax",
        "Email",
        "Website",
        "Product URL template",
        "Parent assignment"
      ],
      "collects": [
        "Name",
        "Comment",
        "Not selectable",
        "Alternative names",
        "Preview attachment",
        "Address",
        "Phone",
        "Fax",
        "Email",
        "Website",
        "Product URL template",
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
      "target": "src/Controller/AdminPages/ManufacturerController.php"
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

# Public manufacturer

Manufacturer information, supported parameters and attachments and relevant history; the source-supported record and nested inputs.
