# Teoria4u device approvals

This repository is public. Never put passwords, API keys, private keys, or other secrets here.

Edit `devices.json` to approve device IDs. Set an ID to `true` to enable it, or `false` to disable it. Missing IDs are disabled. Keep the file valid JSON, with commas between entries:

```json
{
  "devices": {
    "00000000-0000-4000-8000-000000000000": true,
    "00000000-0000-4000-8000-000000000001": false
  }
}
```

Users find their ID and current status in the extension under Advanced. The extension checks the list when a solve starts; revocation does not interrupt a run already in progress. Uninstalling the extension or clearing its data creates a new ID.

IDs are public and are not passwords. This is a simple approval list, not strong device security: an ID can be copied and the extension can be modified.