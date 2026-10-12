---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "p": "Public Web",
    "a": "Authenticated Web"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "user",
      "text": "The caller supplies a recognized barcode for the normal open continuation.",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-scanner"
        },
        "a": {
          "place": "web::authenticated::authenticated-scanner"
        }
      },
      "capability": "scan-label"
    },
    {
      "kind": "product",
      "actor": "user",
      "text": "The Product consults the User configuration for the scanner dialog.",
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
        "p": {
          "place": "web::public::public-scanner"
        },
        "a": {
          "place": "web::authenticated::authenticated-scanner"
        }
      },
      "capability": "scan-label"
    },
    {
      "kind": "product",
      "actor": "user",
      "text": "The Product resolves the found Part lot and carries the caller to its containing component with the lot highlighted.",
      "entities": [
        {
          "entity": "part-lot",
          "effect": "reads",
          "facts": [
            "User barcode",
            "Part assignment"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-scanner"
        },
        "a": {
          "place": "web::authenticated::authenticated-scanner"
        }
      },
      "capability": "scan-label"
    },
    {
      "text": "The caller requests the supported information of one existing selected record.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "browse-parts"
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
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "browse-parts"
    },
    {
      "text": "The Product discloses the selected Part information through this contract.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Comment",
            "Tags",
            "Internal part number",
            "GTIN",
            "Manufacturer product number",
            "Manufacturer URL",
            "Manufacturing status",
            "Minimum desired amount",
            "Favorite",
            "Needs review",
            "Mass",
            "EDA information",
            "Provider reference",
            "Preview attachment",
            "Category assignment",
            "Footprint assignment",
            "Manufacturer assignment",
            "Unit assignment",
            "Custom state assignment",
            "Added at",
            "Modified at",
            "Stock summary"
          ]
        }
      ],
      "contexts": {
        "p": {
          "place": "web::public::public-part"
        },
        "a": {
          "place": "web::authenticated::authenticated-part"
        }
      },
      "capability": "browse-parts"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    }
  ]
}
---

# Scan and open part lot achieved

## Trigger

The same caller follows the source-carried continuation: Resolved Part/lot barcode → Part information.

## Outcome

The resolved component information is disclosed, with the resolved lot highlighted on the lot branch.
