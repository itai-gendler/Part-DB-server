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
  "limitations": [
    "A Part is one kind of thing; individual pieces within a stock lot are not told apart.",
    "KiCad reads Parts from Part-DB as a component library and never changes the inventory.",
    "Single sign-on is delegated to a SAML identity provider; LDAP or Active Directory accounts connect through an intermediary such as Keycloak.",
    "Distributor part information, datasheets and prices come from the information providers an instance configures."
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

## Intent

Part-DB lets hobbyists, makerspaces, small companies and universities keep track of their electronic components, giving everyone who shares an inventory controlled access to it from a browser, without installing additional software.
