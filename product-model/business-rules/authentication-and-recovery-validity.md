---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "sign-in",
      "contexts": [
        {
          "place": "web::public"
        }
      ]
    },
    {
      "type": "capability",
      "id": "reset-password",
      "contexts": [
        {
          "place": "web::public"
        }
      ]
    },
    {
      "type": "capability",
      "id": "change-password",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/UserSystem/PasswordResetManager.php"
    }
  ]
}
---

# Local authentication and recovery validate their credentials and inputs

Local credential/CAPTCHA checks and new-password constraints apply. Recovery stores a verifier and one-day expiry for a found account; successful redemption changes the credential, invalidates recovery data and leaves Password change required unchanged. Unknown requests receive acknowledgment without credential changes; a found account without email can store recovery data without sending mail. Ordinary password change validates the old password and clears the required-change flag.
