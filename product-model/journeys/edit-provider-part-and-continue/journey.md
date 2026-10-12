---
{
  "actors": [
    "user"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Edit provider part and continue

## Goal

Provider-assisted update → ordinary Part editor.

## Success criterion

The saved or surviving record reaches its editor and the same caller’s subsequent valid edit is saved.
