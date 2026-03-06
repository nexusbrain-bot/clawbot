# RESTORE.md - How to Restore Your Data

## If I Forget You (Session Reset)

When the VM restarts or I lose session context, your **files still exist** but you might need to restore from GitHub.

---

## Quick Check: Are Your Files There?

```bash
ls -la /root/.openclaw/workspace/
```

If you see `USER.md`, `MEMORY.md`, `credentials/`, etc. → **Your files are fine!**

Just message me and I'll read them to remember you.

---

## If Files Are Missing: Restore from GitHub

### Option 1: Fresh Clone (Safest)

```bash
# Backup the empty workspace (just in case)
mv /root/.openclaw/workspace /root/.openclaw/workspace.backup

# Clone from GitHub
cd /root/.openclaw
git clone https://github.com/nexusbrain-bot/clawbot.git workspace

# Done! Your files are restored
```

---

### Option 2: Pull Latest (If git repo exists)

```bash
cd /root/.openclaw/workspace

# Check if git is initialized
git status

# If git exists, pull latest
git pull origin master

# If that fails, force reset to GitHub version
git fetch origin
git reset --hard origin/master
```

---

## Your GitHub Backup

**Repository:** https://github.com/nexusbrain-bot/clawbot  
**Clone URL:** https://github.com/nexusbrain-bot/clawbot.git

**Note:** If you need to re-authenticate, message me and I'll help you set up the access token securely.

---

## What Gets Restored

- ✅ USER.md (your profile)
- ✅ MEMORY.md (long-term memory)
- ✅ credentials/titanium_software.txt (API keys)
- ✅ SOUL.md, AGENTS.md, TOOLS.md (configuration)
- ✅ All other workspace files

---

## After Restore

1. **Check files are there:**
   ```bash
   ls -la /root/.openclaw/workspace/
   cat /root/.openclaw/workspace/USER.md
   ```

2. **Message me:** "I restored from backup"

3. **I'll read your files** and remember:
   - Your name (Brian Grant)
   - Your profile
   - Your credentials
   - Our history

---

## Emergency: I Can't Access GitHub

If GitHub is down or you can't access it:

1. **Check if files exist locally:** `/root/.openclaw/workspace/`
2. **Ask me to read them:** "Read my USER.md file"
3. **I'll rebuild context** from local files

---

## Prevention: Regular Backups

I automatically commit and push important changes to GitHub.

You can also manually backup:
```bash
cd /root/.openclaw/workspace
git add -A
git commit -m "Manual backup $(date)"
git push
```

---

**Remember:** GitHub is your safety net. Files persist across VM restarts, but if they're ever lost, GitHub has them.
