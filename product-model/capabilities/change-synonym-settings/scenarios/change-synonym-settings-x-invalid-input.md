---
{
  "kind": "validation",
  "routes": {
    "route": "Administration Web"
  },
  "steps": [
    {
      "text": "The caller submits the failing input: The submitted synonym options input fails its section’s declared constraints.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::administration::system-settings"
        }
      }
    },
    {
      "text": "The Product retains the form’s validation errors for the submitted synonym options input fails its section’s declared constraints. The submitted write is not accepted.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::administration::system-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Settings/AppSettings.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/SettingsController.php"
    }
  ]
}
---

# Change synonym settings — x invalid input

## Trigger

The submitted synonym options input fails its section’s declared constraints.

## Outcome

The submitted synonym options input fails its section’s declared constraints. No successful change synonym settings result is asserted.
