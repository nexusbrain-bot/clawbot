# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

## AgentMail

- **Inbox ID:** limh-nexus@agentmail.to
- **API Key:** Configured in openclaw.json (skills.entries.agentmail.apiKey)
- **API Endpoint:** https://api.agentmail.to/v0/inboxes/{inbox_id}/messages/send
- **Send Email Command:**
  ```bash
  curl -X POST "https://api.agentmail.to/v0/inboxes/limh-nexus@agentmail.to/messages/send" \
    -H "Authorization: Bearer $API_KEY" \
    -H "Content-Type: application/json" \
    -d '{"to":"recipient@example.com","subject":"Subject","text":"Body text"}'
  ```

## Examples

```markdown
### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.
