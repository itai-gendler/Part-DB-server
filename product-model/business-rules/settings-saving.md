---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "product-settings",
      "effect": "changes"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/SettingsController.php"
    }
  ]
}
---

# Valid general settings sections are merged, saved and invalidate reached caches

Accepted general-section input is validated, merged and saved, with reached cache invalidation and source-declared environment overrides taking precedence. Individually addressed provider configuration does not silently become part of general-section editing.
