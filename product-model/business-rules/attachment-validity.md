---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "attachment"
    },
    {
      "type": "entity",
      "id": "attachment-type"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Attachments/Attachment.php"
    }
  ]
}
---

# Attachment references satisfy naming, subject, type and upload constraints

Attachment naming, attached subject/type compatibility and declared upload constraints apply. An internal reference or external URL is not proof that content is available. Private classification is derived from its internal path.
