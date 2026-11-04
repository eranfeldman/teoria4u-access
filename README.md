# Teoria4u device approvals

This repository is public. Never put passwords, API keys, private keys, or other secrets here.

`devices.json` is an approval list. An entry is enabled only when its value is `true`; missing IDs and entries set to `false` are disabled. Example:

```json
{
  "devices": {
    "00000000-0000-4000-8000-000000000000": true,
    "00000000-0000-4000-8000-000000000001": false
  }
}
```

The list is a work in progress: creating this repository alone does not activate enforcement or prevent copied IDs. IDs are public, so they are not passwords.