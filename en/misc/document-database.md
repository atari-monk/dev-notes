## Prefer Documents Over Schemas

For a small, private knowledge base, designing a specialized database schema can be unnecessary complexity.

Instead, store each piece of knowledge as a Markdown document and keep the database model deliberately simple.

```text
documents
---------
id
title
content
created_at
updated_at
```

Optionally, add lightweight metadata:

```text
document_tags
-------------
document_id
tag
```

The actual structure lives inside the document:

```markdown
---
title: Porcelain tiles
category: flooring
price: 25-45 EUR/m²
tags:
  - bathroom
  - flooring
  - ceramic
---

# Porcelain tiles

Dense, low-absorption ceramic material suitable for floors,
walls, bathrooms and kitchens.

## Properties

- Very low water absorption
- Durable
- Easy to clean

## Advantages

Good for bathrooms and high-traffic areas.

## Disadvantages

Can be expensive and difficult to replace if a matching
batch is no longer available.

## Notes

Check slip-resistance rating before using on the bathroom floor.
```

The front matter provides optional structured metadata for things that are useful to filter or index. The Markdown body remains free-form and can evolve without database migrations.

If a property later becomes something that needs frequent querying — for example, price, thermal conductivity, or supplier — it can be promoted to a proper database field.

The goal isn't to avoid databases entirely. It's to **keep the database boring and let the documents contain the knowledge**.
