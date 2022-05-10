---
title: javascript
categories: language
---

## get started

### React Query

```python
function getQuery(search) {
  const result = {}
  if (search.length > 1) {
      const query = search.substring(1)
      const vars = query.split("&")
      for (let i = 0; i < vars.length; i++) {
          let pair = vars[i].split("=")
          if (pair.length === 2) {
            result[pair[0]] = pair[1]
          }
      }
  }
  return result
}
const search = window.location.search
const query = getQuery(search)
```
