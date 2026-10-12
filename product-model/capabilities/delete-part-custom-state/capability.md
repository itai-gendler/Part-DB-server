---
{
  "availability": [
    {
      "place": "web::public"
    },
    {
      "place": "web::authenticated"
    },
    {
      "place": "rest-api"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartCustomState.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/PartCustomStateController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    }
  ],
  "domain": "part-custom-states"
}
---

# Delete part custom state

The selected Part custom state is removed through the implemented deletion path.
