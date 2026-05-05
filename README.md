# PartProof — Releases & Issues

Public distribution channel for **PartProof Copilot**, an AI-driven
CAD copilot for SOLIDWORKS.

The product source code lives in a separate, private repository.
This repo's purpose is to host:

1. **Release downloads** — channel-specific MSI installers (stable,
   beta, dev), accessed by the in-app auto-updater and by manual
   download via the [Releases tab](../../releases).
2. **Issue tracking** — secondary channel for tester bug reports and
   feature requests. Discord remains the primary support channel for
   active testers; this is for users who prefer the GitHub workflow.
3. **Update manifests** — per-channel appcast XML feeds polled by
   PartProof's NetSparkle-based auto-updater.

## How to install

1. Download the latest **`PartProof-Copilot-<version>.zip`** for your
   channel from the [Releases tab](../../releases).
2. Extract the zip.
3. Right-click `Install-PartProof.ps1` → **Run with PowerShell**, or
   double-click the `.msi` directly.
4. Launch SOLIDWORKS. The PartProof task pane appears under the
   Add-Ins tab.

The MSI handles in-place upgrades from older versions automatically;
no need to uninstall first.

## Release channels

| Channel | Tag pattern | Audience |
|---|---|---|
| **stable** | `v0.X.Y` (no suffix) | General availability |
| **beta** | `v0.X.Y-beta.N` | Invited testers |
| **dev** | (not published here) | Maintainer-local channel; rebuilt from private source |

Beta and dev installs use channel-specific paths and ports so all
three can coexist on the same machine.

## Auto-update (planned, beta in progress)

Once the auto-updater ships, the in-app **Check for Updates** action
polls `appcast/<channel>.xml` from this repo and surfaces a prompt
when a newer version is available. Cross-channel jumps (e.g., beta →
stable) never happen automatically — each install only sees its
own channel's feed.

## Reporting issues

- **Discord** is the fastest path; ping in the tester channel for
  active beta participants.
- **GitHub Issues** (this repo) is the alternate path. Use the
  templates: bug report, feature request, or question.
- Security issues: please use [GitHub Security Advisories](../../security/advisories/new)
  rather than a public issue.

## Privacy note for tester-submitted bundles

PartProof's "Send Diagnostic Bundle" feature in the addin currently
targets Discord with full log + transcript content. **If you choose
to file an issue on GitHub instead and attach a diagnostic bundle,
remember that the issue and any attachments are public.** Bundles
may include file paths, chat transcripts, and CAD parameter values —
review and redact before posting.

## License

The MSI binaries distributed in this repo's Releases are licensed
under the PartProof Tester License Agreement included with each
installer. The repo content (README, issue templates, appcast XML)
is provided as-is for distribution purposes.
