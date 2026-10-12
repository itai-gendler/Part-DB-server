---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/LogSystem/AbstractLogEntry.php"
    }
  ],
  "domain": "activity-log"
}
---

# Activity entry

A kept activity record identifying an event and its target. Its retained actor name is separate from the surviving User relation.

## Information kept

- **Actor name** — The retained actor-name text.
- **Occurred at** — When the event occurred.
- **Event kind** — The recorded kind of event.
- **Severity** — The source-declared event severity.
- **Access method** — The recorded access method.
- **Target reference** — The referenced target class and identity.
- **Event details** — The source-defined details associated with the event kind.
- **Request correlation** — The request correlation identifier.
- **Transaction correlation** — The transaction correlation identifier.
