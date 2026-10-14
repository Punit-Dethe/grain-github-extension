# Published tester update — 14 October 2026

Version 0.1.1 declares public `transport.headers.x-mcp-toolsets = all`.
The maintained CLI reports **doctor: 0 findings** and produces the canonical
0.1.1 descriptor. The MCP URL, OAuth authentication declaration and extension
identity are unchanged. There is no native bundle or embedded credential.

The shared Grain source validates options, preserves signed artifact/revision
ownership and forwards them through the official SDK. Version 0.1.1 is published
at catalogue index 4, registry commit `36704a63fd14bcabb28a4bc5a4f349fed2010ddc`.
The exact source tag is `v0.1.1`, commit `394176037b46ecbfde34d7af0996a505b3352400`;
later documentation commits do not move that tag or change the signed source.
Maintainer approval was explicit for this tester update; other packages retain
their independent review requirements. Genuine CI preparation/attestation and
signing passed. Independent public delivery verified signatures, addressed
assets, the mutable app URL and pinned-commit bytes across 54 HTTP requests.
Matching installed-alpha update/account/Agent acceptance is still pending.
One tester artifact build is running; no application release was published.

The previous installed alpha passed private README read/restart, one issue
creation and one branch creation. Those results do not certify this candidate,
all GitHub actions or every account permission. No failed write was replayed.

The earlier record below is retained as dated history, not current status.

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
