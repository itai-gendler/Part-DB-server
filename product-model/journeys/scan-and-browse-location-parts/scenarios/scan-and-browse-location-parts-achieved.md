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
      "text": "The Product resolves the found Storage location and carries the caller to the component list filtered by it.",
      "entities": [
        {
          "entity": "storage-location",
          "effect": "reads",
          "facts": [
            "Name"
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
      "text": "The caller requests matching records with supported search, filter or selection input.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "web::public::public-part-list"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-list"
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
          "place": "web::public::public-part-list"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-list"
        }
      },
      "capability": "browse-parts"
    },
    {
      "text": "The Product discloses matching Part information through this contract.",
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
          "place": "web::public::public-part-list"
        },
        "a": {
          "place": "web::authenticated::authenticated-part-list"
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

# Scan and browse location parts achieved

## Trigger

The same caller follows the source-carried continuation: Location barcode → Part list filtered by Location.

## Outcome

The carried component list discloses matching records filtered by the resolved Location.
