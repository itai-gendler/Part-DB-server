---
{
  "entities": [
    {
      "entity": "user",
      "collects": [
        "Username",
        "Password credential"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/SecurityController.php"
    }
  ]
}
---

# Sign in

Local sign-in input and authentication feedback, including required continuation.
