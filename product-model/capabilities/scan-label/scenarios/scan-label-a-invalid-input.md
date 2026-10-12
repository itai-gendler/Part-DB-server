---
{
  "kind": "validation",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The barcode format is unrecognized or cannot be interpreted by the selected mode.",
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
      "text": "The Product reports the unrecognized or invalid barcode and returns to the scanner without a resolved destination.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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

# Scan label — Authenticated Web invalid input

## Trigger

The barcode format is unrecognized or cannot be interpreted by the selected mode.

## Outcome

The barcode format is unrecognized or cannot be interpreted by the selected mode. No successful scan label result is asserted.
