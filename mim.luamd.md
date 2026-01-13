---
name: check-products
description: "Инструмент для проверки товаров"
version: 1.0.2               # Игнорируется Claude, полезно для CI/CD
author: "Mimikkai"           # Игнорируется Claude
license: MIT
allowed-tools: [lua]

mim:
  columns:
    A:
      label: "Название"
      description: "Наименование товара"
      field_type: "STRING"
      is_required: true
      read_only: false
    B:
      label: "Категория"
      description: "Категория товара"
      field_type: "STRING"
      is_required: true
      read_only: false
    C:
      label: "Цена"
      description: "Цена товара в рублях"
      field_type: "NUMBER"
      is_required: true
      read_only: false
---

```lua
-- Допустим, весь frontmatter доступен в переменной `meta`
local cols = mim.columns
```

Проанализируй строку из каталога продуктов.
Проверь корректность названия, категории и цены.
Если находишь ошибки - предложи исправления.
