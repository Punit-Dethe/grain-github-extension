# Initial verification — 9 October 2026

This is a **publication candidate**, not a certified live GitHub connection.

| Check                                   | Result           | Scope                                                                               |
| --------------------------------------- | ---------------- | ----------------------------------------------------------------------------------- |
| `grain-ext doctor`                      | Pass, 0 findings | Current MCP descriptor and listing/media validation                                 |
| `grain-ext pack`                        | Pass             | Canonical `com.grain.github-0.1.0.mcp.json`, no credentials or native worker        |
| Store artwork                           | Inspected        | GitHub's provided lockup rendered in supported WebP media; source marks retained    |
| Official remote MCP endpoint            | HTTP 401         | Unauthenticated initialize correctly requires an access token                       |
| Protected resource discovery            | HTTP 200         | Resource is the configured MCP endpoint; issuer is `https://github.com/login/oauth` |
| Authorization discovery                 | HTTP 200         | S256 PKCE advertised; no dynamic registration endpoint advertised                   |
| GitHub account sign-in and actual tools | Pending          | Needs a registered app and account consent in Grain                                 |
| Public store publication/installation   | Pending          | Needs reviewed submission, signing/operator setup and catalogue activation          |

Preflight sent one unauthenticated initialize request and read public discovery
metadata only. It performed no tool call, GitHub account action or write. No
provider credentials, account data or private signing keys were accessed.

Public source references:

- [Official GitHub MCP server](https://github.com/github/github-mcp-server).
- [Remote host authentication](https://github.com/github/github-mcp-server/blob/main/docs/host-integration.md).
- [GitHub authentication discovery](https://docs.github.com/en/apps/github-authentication-discovery-endpoints).
- [Integration artwork](https://brand.github.com/foundations/logo).

Actual registry preparation evidence and its pinned source commit belong with
the generated submission/build receipt. Do not treat a successful local package
or a GitHub source repository as an activated store release.
