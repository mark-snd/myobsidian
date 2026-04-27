---
tags: [coding, dev]
---

## Steps to Add [mark@snd-labs.com](mailto:mark@snd-labs.com)

### 1. Authorize the new account

Run this command (it will open a browser for Google OAuth):

```bash
export GOG_KEYRING_PASSWORD=korea123
gog auth add mark@snd-labs.com --services calendar
```

If you also want Gmail/Drive access later, use:

```bash
gog auth add mark@snd-labs.com --services calendar,gmail,drive
```

### 2. Complete OAuth in browser

- Sign in with your `mark@snd-labs.com` account
- Grant the requested permissions
- The token will be stored in your keyring

### 3. Verify it worked

```bash
export GOG_KEYRING_PASSWORD=korea123
gog auth list
```

You should see both accounts listed.

### 4. Using the accounts

**Option A: Specify per-command** (recommended for multiple accounts)

```bash
gog calendar events primary --account mark@snd-labs.com --from 2026-02-01 --to 2026-02-08
```

**Option B: Set default account** If you want Echo to default to your business account, update `~/.openclaw/.env`:

```
GOG_ACCOUNT=mark@snd-labs.com
```

**Option C: Set up an alias**

```bash
gog auth alias add work mark@snd-labs.com
gog auth alias add personal 87mkim@gmail.com
```

Then use: `gog calendar events primary --account work`