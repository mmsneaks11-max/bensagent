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

## 🔁 Handoff Paths
- Index: `~/clawd/shared/handoffs/INDEX.md`
- cleopatra → scout: `~/clawd/shared/handoffs/cleopatra-to-scout/`
- scout → coach: `~/clawd/shared/handoffs/scout-to-coach/`
- scout → lila: `~/clawd/shared/handoffs/scout-to-lila/`
- pixel → lila: `~/clawd/shared/handoffs/pixel-to-lila/`
- pixel → clawd: `~/clawd/shared/handoffs/pixel-to-clawd/`
- kay → byte: `~/clawd/shared/handoffs/kay-to-byte/`
- byte → kay: `~/clawd/shared/handoffs/byte-to-kay/`

## 📚 ECHO (Institutional Memory)
- Home: `~/clawd/hive/echo/`
- Registry: `~/clawd/hive/echo/index/registry.md`
- Patterns: `~/clawd/hive/echo/patterns/`
- Immutables: `~/clawd/hive/IMMUTABLES.md`


## 📟 Pager System (ECHO Interrupt Protocol)
- **AgentDeck/AgentDock URL (Mac1 local):** http://localhost:23456
- **Remote (Mac2/PC1):** http://100.109.230.90:23456
- **Shared file:** `~/clawd/shared/echo_interrupts.json`

**Send a page:**
```bash
curl -s -X POST http://localhost:23456/api/interrupt   -H 'Content-Type: application/json'   -d '{
    "from": "<your-agent-id>",
    "to": ["<target-agent-id>"],
    "urgency": "normal",
    "category": "agent_request",
    "summary": "One-line pager summary",
    "context": "Enough context to act immediately"
  }'
```

**Check pages:**
```bash
curl -s http://localhost:23456/api/interrupts
```

**Acknowledge:**
```bash
curl -s -X POST http://localhost:23456/api/interrupt/<id>/read   -H 'Content-Type: application/json'   -d '{"agentId":"<your-agent-id>"}'
```
