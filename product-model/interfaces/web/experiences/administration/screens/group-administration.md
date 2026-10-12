---
{
  "entities": [
    {
      "entity": "group",
      "shows": [
        "Name",
        "Comment",
        "Permission overrides",
        "Enforce second factor",
        "Parent assignment",
        "Added at",
        "Modified at"
      ]
    },
    {
      "entity": "user",
      "shows": [
        "Username",
        "Personal profile"
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
      "target": "src/Controller/GroupController.php"
    }
  ]
}
---

# Group administration

Inspected grouping, inheritance, membership and history information.
