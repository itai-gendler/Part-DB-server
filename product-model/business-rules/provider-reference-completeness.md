---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "part",
      "facts": [
        "Provider reference"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    }
  ]
}
---

# Provider keys and external references are complete together

Provider key and external reference must be supplied together under the source validation; provider update time follows the supported reference rules.
