# Teoria4u device approvals

This repository is public. Never put passwords, API keys, private keys, or other secrets here.

Edit `devices.json` to approve device IDs. Set an ID to `true` to enable it, or `false` to disable it. Missing IDs are disabled. Keep the file valid JSON, with commas between entries:

```json
{
  "devices": {
    "12345678": true,
    "87654321": false
  },
  "comments": {
    "12345678": "Alex - laptop",
    "87654321": "Sam - old computer"
  }
}
```

Each installation has a random eight-digit ID. Users upgrading from an older UUID ID receive a new ID and need to be approved again. Use the optional `comments` section to add notes for each ID; comments do not affect access. JSON does not support `//` or `#` comments. This repository is public, so avoid personal or sensitive details. Users find their ID and current status in the extension under Advanced. The extension checks the list when a solve starts; revocation does not interrupt a run already in progress. Starting with version 3.18.0, each new version generates a new ID that must be approved. Reloading the same version keeps its ID; reinstalling creates a new one. Older versions may still allow restoring an ID, so disable old IDs when moving users to the new version.

IDs are public and are not passwords. This is a simple approval list, not strong device security: an ID can be copied and the extension can be modified.
A signed GitHub webhook refreshes the approval service after pushes to main, and the Worker refreshes it every 15 minutes. Access checks use its stored data and fail closed if it has not refreshed for 45 minutes. The local dashboard refreshes activity every 15 seconds and can edit this file through the owner’s local GitHub login. The service records each approved device ID, authorized solve-start count, and most recent start time for the owner’s password-protected local dashboard. It does not collect questions or answers. Counts are reported by the extension and may be spoofed.
