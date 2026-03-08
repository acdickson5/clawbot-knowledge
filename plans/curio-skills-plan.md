# Curio Skills Plan

**Date:** 2026-03-08
**For:** Curio (local Mac Mini agent)
**Purpose:** Help Holly with eBay store, image editing, content creation

---

## Priority 1: Essential Skills (Immediate Need)

### Image Processing & Editing
| Skill | Purpose | Status |
|-------|---------|--------|
| **image-magik-resize** | Resize images using ImageMagick | Available - install via ClawHub |
| **video-frames** | Extract frames from videos (for content) | ✅ Already enabled |
| **nano-pdf** | Edit PDFs with natural language | ✅ Already enabled |
| **smart-ocr** | OCR text from images (includes image processing) | Available |

**Installation:**
```bash
# Install ImageMagick first
brew install imagemagick

# Then install skills
npx clawhub@latest install image-magik-resize
npx clawhub@latest install smart-ocr
```

### File & System Management
| Skill | Purpose | Status |
|-------|---------|--------|
| **git-sync** (custom) | Pull/push knowledge repo | ✅ Created and working |
| **exec** | Run shell commands | ✅ Enabled |
| **fs** | File system operations | Built-in |

---

## Priority 2: eBay & Business Operations

### Communication & Messaging
| Skill | Purpose | Status |
|-------|---------|--------|
| **bluebubbles** | iMessage integration for Holly | ⚠️ Blocked - needs setup |
| **wacli** | WhatsApp CLI | ⚠️ Blocked - needs install |
| **imsg** | iMessage/SMS via Messages.app | ✅ Already enabled |

**Note:** BlueBubbles is the best option for Holly's iPad. Requires:
1. Install BlueBubbles server on Mac Mini
2. Configure skill with server URL
3. Test iPad → Mac Mini → Curio flow

### Content & Marketing
| Skill | Purpose | Status |
|-------|---------|--------|
| **openai-image-gen** | Generate images for listings | ✅ Already enabled (has API key) |
| **summarize** | Summarize product descriptions | ✅ Already enabled |
| **sag** | ElevenLabs TTS for voice content | ✅ Already enabled (has API key) |

---

## Priority 3: Advanced Capabilities (Post-NAS Setup)

### NAS & Storage Management
**Custom skills needed:**
- `nas-backup` - Automated backup to Synology
- `file-organizer` - Sort art files by date/project
- `photo-curate` - Organize iPad/iPhone photos

### Printer Management
**Custom skill needed:**
- `printer-router` - Send jobs to right printer (SC-P900 for art, ET-3850 for color, etc.)

### eBay Automation
**Custom skills needed:**
- `listing-generator` - Create eBay listings from photos
- `price-checker` - Research comparable sales
- `inventory-tracker` - Manage stock levels

---

## Skills Already Enabled (from Adam's setup)

From the Control Panel, Curio currently has:
- ✅ apple-notes
- ✅ apple-reminders
- ✅ blucli
- ✅ clawhub
- ✅ gh-issues
- ✅ github
- ✅ gog (Google Workspace)
- ✅ healthcheck
- ✅ imsg
- ✅ model-usage
- ✅ nano-pdf
- ✅ openai-image-gen
- ✅ openai-whisper
- ✅ sag (ElevenLabs TTS)
- ✅ session-logs
- ✅ skill-creator
- ✅ summarize
- ✅ video-frames
- ✅ weather
- ✅ git-sync (custom created)

---

## Immediate Action Items

1. **Install ImageMagick:** `brew install imagemagick`
2. **Install image-magik-resize skill:** `npx clawhub@latest install image-magik-resize`
3. **Set up BlueBubbles** for Holly's iPad access
4. **Test image resizing** with a sample photo
5. **Create custom skill** for printer routing

---

## Custom Skills to Build

### 1. printer-router
**Purpose:** Route print jobs to correct printer based on job type
**Printers:**
- Epson SC-P900 → Art prints, gallery pieces
- Epson ET-3850 → General color printing
- Brother HL-3170CDW → Color laser (documents)
- CTP800BD → Shipping labels
- HP Envy 5642 → General purpose

### 2. nas-backup (when NAS arrives)
**Purpose:** Automated backup to Synology DS220+
**Features:**
- Backup iPad photos automatically
- Sync art files
- RAID 1 monitoring

### 3. listing-generator
**Purpose:** Create eBay listings from photos
**Features:**
- Extract item details from photos
- Generate titles and descriptions
- Suggest pricing
- Create listing drafts

---

## Resources

- **ClawHub (skills registry):** https://www.clawhub.ai/
- **Awesome OpenClaw Skills:** https://github.com/VoltAgent/awesome-openclaw-skills
- **Skill Creator Guide:** `/opt/homebrew/lib/node_modules/openclaw/skills/skill-creator/SKILL.md`

---

*Next update: After NAS setup and BlueBubbles configuration*
