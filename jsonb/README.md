# Usage

### JSONB_EDIT

```sql
JSONB_EDIT(obj JSONB, keys_to_remove TEXT[], obj_to_merge JSONB)
```

Returns a `JSONB` object after applying the desired changes. Only the first argument is required.

```sql
SELECT JSONB_EDIT(
  '{"abc": 123, "def": "my string", "ghi": "my other string", "jkl": "hello world"}'::JSONB,
  ARRAY['def', 'ghi']::TEXT[],
  '{"ghi": "edited", "jkl": "good bye"}'::JSONB
);

-- Returns:
{"abc": 123, "ghi": "edited", "jkl": "good bye"}
```
