---
{
  "entities": [
    {
      "entity": "label-profile",
      "shows": [
        "Name",
        "Comment",
        "Options",
        "Show in dropdown",
        "Preview attachment",
        "Added at",
        "Modified at"
      ],
      "collects": [
        "Name",
        "Comment",
        "Options",
        "Show in dropdown",
        "Preview attachment"
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
      "target": "src/Controller/AdminPages/LabelProfileController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Form/AttachmentFormType.php"
    }
  ]
}
---

# Public label profile

Saved label information, options, preview selection and supported history; profile and attachment inputs.
