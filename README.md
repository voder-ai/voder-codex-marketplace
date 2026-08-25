# Voder Codex Marketplace

This public marketplace provides **Voder Early Access** for Codex. It connects
to Voder's existing production MCP service and OAuth flow; it does not create a
separate service, account entitlement or data store.

Early Access means Voder capabilities may be available here before OpenAI
completes the separate review of a new ChatGPT Store version. Availability here
is not evidence of ChatGPT Store approval or publication.

## Install

### Codex desktop

1. Open **Plugins**.
2. Choose **Add** and then **Add a marketplace**.
3. Enter `voder-ai/voder-codex-marketplace`.
4. Install **Voder Early Access** and complete Voder authentication when asked.

### Codex CLI

```sh
codex plugin marketplace add voder-ai/voder-codex-marketplace
codex plugin add voder-early-access@voder
```

Start a new Codex task after installation so the plugin tools are available.

## Update

```sh
codex plugin marketplace upgrade voder
```

## Remove

```sh
codex plugin remove voder-early-access
codex plugin marketplace remove voder
```

## Service and policies

- [Voder](https://voder.ai/)
- [Privacy Policy](https://voder.ai/privacy/)
- [Terms of Service](https://voder.ai/terms/)
- [Support](https://voder.ai/support/)
- [Security](SECURITY.md)
