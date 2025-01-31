---
tags:
  - sql
---

# SQL Backup with Blobs can not be reimported

- If the sql file has `0x` in the column of the blob but not a real image etc. Make sure that the `0x` is replaced with `null` before importing the sql file.