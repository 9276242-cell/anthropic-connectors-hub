# Daily Sync Runbook for Apple M5 and Claude Code

Standard operating procedure for two-way synchronization between online `claude.ai/code` web development sessions and the local Apple M5 workstation.

---

## 1. Operating Architecture

Development is divided strategically across two complementary environments:

```
                  ┌──────────────────────────────────────────────┐
                  │                 GitHub Cloud                 │
                  │             Central Repository Hub           │
                  └──────────────▲────────────────▲──────────────┘
                                 │                │
                        Git Push │                │ Direct Integration
                        Git Pull │                │ Web Sessions
                                 ▼                ▼
                     ┌───────────────────────┐ ┌───────────────────────┐
                     │    Local Apple M5     │ │  claude.ai/code Cloud │
                     ├───────────────────────┤ ├───────────────────────┤
                     │ Hardware Engine       │ │ Online Collaboration  │
                     │ Antigravity Execution │ │ Fable & David Agents  │
                     │ Local Database Mocks  │ │ PRs & Issue Triage    │
                     │ Secure Final Test Run │ │ Prompt Engineering    │
                     └───────────────────────┘ └───────────────────────┘
```

---

## 2. Morning Routine: Pulling Online Progress to Apple M5

Before beginning local testing or running hardware-intensive verification on Apple M5:

1. Open Terminal on Apple M5.
2. Navigate to the repositories folder:
   ```bash
   cd "/Users/anasmahmood/khanwco-repos"
   ```
3. Pull the latest commits merged by Fable and David:
   ```bash
   for repo in "Anthropic Connectors Hub" "hse" "isa" "isoerp-mcp" "isoerp-next"; do
     echo "=== Updating $repo ==="
     git -C "$repo" pull --rebase origin main
   done
   ```

---

## 3. Evening Routine: Syncing Local Progress to GitHub

At the close of each day or after passing local testing suites on Apple M5:

1. Stage all changes across updated repositories:
   ```bash
   cd "/Users/anasmahmood/khanwco-repos/Anthropic Connectors Hub"
   git status
   git add -A
   git commit -m "Daily progress sync from Apple M5: connector manifests and reviewer packs"
   git push origin main
   ```
2. Verify all commits appear on GitHub so Fable and David can continue uninterrupted in their next `claude.ai/code` web session.

---

## 4. Conflict Resolution Rules

* **Main Branch Stability**: Always rebase rather than merge when pulling updates from online sessions (`git pull --rebase origin main`).
* **Clean Commits**: Keep commit messages clear, descriptive, and human-readable.
* **No Unsaved Local Drift**: Never leave unstaged or uncommitted code on Apple M5 overnight; commit to a topic branch if a feature is still under active development.
