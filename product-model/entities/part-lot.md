---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/PartLot.php"
    }
  ]
}
---

# Part lot

A quantity or explicitly unknown quantity of one Part, with storage, optional ownership and stocktaking information.

## Information kept

- **Description** — The lot description.
- **Comment** — The lot comment.
- **Amount** — The kept quantity; the getter applies the Part’s integer-unit interpretation.
- **Unknown amount** — Whether the quantity is unknown.
- **Needs refill** — Whether this lot is marked for refill.
- **Expiration date** — The optional expiration date.
- **User barcode** — The optional user-defined barcode identifying this lot.
- **Last stocktake** — The time of the last stocktake.
- **Part assignment** — The Part whose stock this lot holds.
- **Location assignment** — The optional Storage location.
- **Owner assignment** — The optional User owning this lot.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.
