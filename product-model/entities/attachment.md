---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Attachments/Attachment.php"
    }
  ]
}
---

# Attachment

A named internal file or external URL attached to a supported subject. The same information list applies to all fourteen supported subject classes. Upload instructions are transient.

## Information kept

- **Name** — The attachment name.
- **Original filename** — The original filename.
- **Internal file reference** — The reference to an internally stored file.
- **External URL** — The externally hosted content URL.
- **Show in table** — Whether this attachment is shown in attachment tables.
- **Subject assignment** — The subject to which the attachment belongs.
- **Type assignment** — The assigned Attachment type.
- **Content classification** — Derived internal or external classification and private classification from the file reference.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
