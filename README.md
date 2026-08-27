# Voder Custom Marketplace

This public custom marketplace provides **Voder Early Access** through ChatGPT
desktop's **Plugins** area and the Codex CLI. It connects to Voder's existing
production MCP service and OAuth flow; it does not create a separate service,
account entitlement, schema, or data store.

Early Access means Voder capabilities may be available through this custom
marketplace before OpenAI completes the separate review of a new ChatGPT Store
version. Availability here is not evidence of ChatGPT Store approval or
publication.

Voder's Xero accounting actions are read-only. The plugin can also record
optional product feedback; that capability does not grant accounting write
access.

## Before you start

1. Use a current ChatGPT desktop app with **Plugins**, or a current Codex CLI
   with `codex plugin` support.
2. [Sign in to Voder](https://app.voder.ai/login).
3. In Voder, connect the intended Xero organisation. Voder requests read-only
   accounting access.

## Install in ChatGPT desktop

1. Open **Plugins**.
2. If your desktop build offers **Add**, then **Add a marketplace**, choose it
   and enter `voder-ai/voder-codex-marketplace`. If that control is absent, use
   the Codex CLI commands below, restart ChatGPT desktop, and return to
   **Plugins**.
3. Choose the **Voder** marketplace and install **Voder Early Access**.
4. Complete Voder OAuth when ChatGPT opens the sign-in flow.
5. Start a new chat so the newly installed tools can load.
6. Ask, “Which Voder tools are available?” Then make one safe read by asking,
   “Which Xero organisations can I access?”

## Install with Codex CLI

```sh
codex plugin marketplace add voder-ai/voder-codex-marketplace
codex plugin add voder@voder
```

Complete Voder OAuth when prompted, then start a new Codex CLI session. Verify
the installation by asking which Voder tools are available, followed by which
Xero organisations you can access.

## Compare FYTD Profit and Loss by tracking option

Tracking category and option names vary by Xero organisation. Discover the
available names before asking for a filtered comparison:

1. Ask: “Which tracking categories and options are available in my connected
   Xero organisation?”
2. Choose one category and option from that answer.
3. Ask: “Compare Profit and Loss for this financial year to date with the same
   period last year, filtered by tracking category `<category name>` and option
   `<option name>`.”

Example for Voder's Demo Company only: if the first answer lists the category
**Region** and the option **Eastside**, ask: “Compare Profit and Loss for this
financial year to date with the same period last year, filtered by Region:
Eastside.” Do not assume those names exist in another Xero organisation.

## Update

In ChatGPT desktop, open **Plugins**, open **Voder Early Access**, and choose
**Refresh** when that control is available. In Codex CLI, refresh the
marketplace snapshot:

```sh
codex plugin marketplace upgrade voder
```

Start a new chat or CLI session after an update.

## Remove

In ChatGPT desktop, open **Voder Early Access** from **Plugins** and use its
remove or uninstall action when offered. A managed workspace may instead show
**Installed by admin**; ask that workspace's admin to change the installation
policy. To remove a local Codex CLI installation and marketplace:

```sh
codex plugin remove voder@voder
codex plugin marketplace remove voder
```

Removing the plugin or marketplace does not disconnect the Xero organisation
from Voder. Manage that connection separately in Voder.

## Troubleshooting

- **The marketplace is not listed:** confirm the repository is exactly
  `voder-ai/voder-codex-marketplace`. If the desktop Add control is absent, use
  the CLI install commands above, restart ChatGPT desktop, and return to
  **Plugins**. In Codex CLI, run `codex plugin marketplace list`, then retry the
  marketplace upgrade.
- **Voder is missing from an existing chat or CLI session:** start a new chat or
  session after installation or update.
- **OAuth did not complete:** reopen Voder Early Access from **Plugins**, or run
  the CLI install command again once. Complete the browser flow and return to
  the client. Do not repeat an ambiguous authentication attempt.
- **The intended Xero organisation is missing:** sign in to Voder and confirm
  that exact organisation is connected before retrying the read.
- **The ChatGPT Store has an older Voder version:** this custom marketplace is a
  separate Early Access channel. Its availability does not change or prove the
  Store version's review status.
- **You are still stuck:** contact [Voder support](https://voder.ai/support/)
  with the failing step and the exact error text. Do not include financial data,
  tokens, tenant identifiers, or credentials.

## Service and policies

- [Voder](https://voder.ai/)
- [Privacy Policy](https://voder.ai/privacy/)
- [Terms of Service](https://voder.ai/terms/)
- [Support](https://voder.ai/support/)
- [Security](SECURITY.md)
