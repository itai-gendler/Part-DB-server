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

# Password reset

Recovery identification, CAPTCHA, recovery credential and new password input; request and redemption form one process.
