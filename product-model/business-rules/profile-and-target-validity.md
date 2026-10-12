---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "label-profile"
    },
    {
      "type": "capability",
      "id": "generate-labels",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "rest-api"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/State/LabelGenerationProcessor.php"
    }
  ]
}
---

# Profiles and generated target sets satisfy their declared validity

Profile Name and supported target type form the source uniqueness boundary. Ranges must resolve a nonempty found target set. Found IDs can be processed even when some requested IDs are absent; wholly absent targets fail. Saved-profile read and actual target checks remain distinct from option-edit controls.
