# Teoria4u device approvals

This repository is public. Never put passwords, API keys, private keys, or other secrets here.

Edit `devices.json` to approve device IDs. Set an ID to `true` to enable it, or `false` to disable it. Missing IDs are disabled. Keep the file valid JSON, with commas between entries:

```json
{
  "devices": {
    "12345678": true,
    "87654321": false
  }
}
```

Each installation has a random eight-digit ID. Users upgrading from an older UUID ID receive a new ID and need to be approved again. Users find their ID and current status in the extension under Advanced. The extension checks the list when a solve starts; revocation does not interrupt a run already in progress. The ID survives extension updates and reloads. Uninstalling clears local data; save the old ID and use Advanced > Restore device ID after reinstalling.

IDs are public and are not passwords. This is a simple approval list, not strong device security: an ID can be copied and the extension can be modified.