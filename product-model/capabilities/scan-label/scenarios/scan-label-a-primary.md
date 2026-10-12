---
{
  "kind": "primary",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits a recognized local component barcode for information mode.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-scanner"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-scanner"
        }
      }
    },
    {
      "text": "The Product resolves the recognized barcode to an existing Part and presents the found information.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Internal part number",
            "GTIN",
            "Provider reference"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-scanner"
        }
      }
    }
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
      "target": "src/Controller/ScanController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/LabelSystem/BarcodeScanner/BarcodeScanResultHandler.php"
    }
  ]
}
---

# Scan label — Authenticated Web primary

## Trigger

The caller submits a recognized local component barcode for information mode.

## Outcome

The caller sees the decoded and found information; direct-open continuations are represented by their Journeys.

## Edge cases

- Lot and location codes resolve their corresponding retained records where found.
- Unknown or invalid input does not imply that a found inventory instance was read.
