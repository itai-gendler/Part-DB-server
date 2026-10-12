---
{
  "id": "part-db-server",
  "summary": "Shared electronic-parts inventory with stock lots, purchasing information, project BOMs, labels, attachments and activity history.",
  "category": "inventory-management",
  "tags": [
    "electronics",
    "inventory"
  ],
  "authors": [
    {
      "name": "Part-DB project",
      "url": "https://github.com/Part-DB/Part-DB-server"
    }
  ],
  "license": "AGPL-3.0-or-later",
  "languages": [
    "en",
    "de",
    "it",
    "fr",
    "ru",
    "ja",
    "cs",
    "da",
    "zh",
    "pl",
    "hu",
    "ko",
    "el",
    "es",
    "nl",
    "hr",
    "pt-BR",
    "uk",
    "vi"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartLot.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/ProjectSystem/ProjectBOMEntry.php"
    }
  ]
}
---

# Part-DB

Part-DB keeps a shared electronic-parts inventory. People classify Parts, identify where their stock lots are stored, keep purchasing information and attachments, prepare project bills of materials, adjust stock and produce labels. Personal settings, configurable permissions and activity history support shared use. Browser, REST, MCP and KiCad component-library contracts expose their source-declared portions of this work.
