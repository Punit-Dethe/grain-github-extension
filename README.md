# GitHub for Grain

A Grain-authored MCP extension connecting the Agent to
[GitHub's official remote MCP server](https://github.com/github/github-mcp-server).
GitHub operates the server at `https://api.githubcopilot.com/mcp/`; this repository
contains only the Grain extension definition and store listing. There is no native
worker, JavaScript bundle, local MCP process or custom GitHub API implementation.

## Status

Version **0.1.0** is an initial publication candidate, not an activated public
store release. Package validation and unauthenticated endpoint checks do not
prove account sign-in or tool execution. See [verification](VERIFICATION.md).

Grain's current installation/account/runtime machinery supports this descriptor.
GitHub does not support dynamic OAuth client registration. Until Grain's own
registered application is integrated, a developer must configure a dedicated
GitHub OAuth/GitHub App's client credentials through Grain's existing account
controls. A successful Linear login does not establish GitHub authentication.
See [GitHub's host integration guide](https://github.com/github/github-mcp-server/blob/main/docs/host-integration.md).

Ordinary users of the eventual supported release should install and sign in
without registering apps, entering client credentials or editing JSON. That
onboarding is still pending; do not advertise this candidate as one-click ready.

## Package and submit

Use the maintained CLI from the Grain checkout; no npm install/build is needed:

```powershell
cargo build --locked -p grain-ext-cli --bin grain-ext
# Run the resulting grain-ext executable from this repository:
grain-ext doctor
grain-ext pack
```

The artifact is `com.grain.github-0.1.0.mcp.json`. `DESCRIPTION.md` is store copy;
README is maintainer documentation. `media/cover.webp` is the signed store artwork.
The original GitHub integration marks are under `assets/`; see their
[attribution and terms](assets/README.md).

After committing source and tagging the reviewed version, use the actual full
commit SHA rather than an example pin:

```powershell
grain-ext submit --registry C:\path\to\grain-extensions --repo https://github.com/Punit-Dethe/grain-github-extension --tag v0.1.0 --commit <actual-full-commit-sha> --license MIT --contact https://github.com/Punit-Dethe/grain-github-extension/issues
```

The generated registry submission needs the existing independent source review,
build, signing and publication route before the public store can offer it.
`grain-ext dev` and Load unpacked are native-worker workflows; do not use them
to claim installation of this MCP package. Test installation from a verified
catalogue through the existing MCP store route.

## Account and acceptance

GitHub app registration uses Grain's displayed loopback callback URI. Verify
the provider-supported desktop OAuth/PKCE and client-secret approach before
offering Grain-owned sign-in. Never commit credentials, private signing keys,
authorization headers or personal tokens into this project or its descriptor.
Store credentials only through Grain's existing vault controls, scoped to this
installed extension rather than a different Developer provider or custom MCP.

Initial real-provider acceptance uses a disposable repository:

1. Browse the published listing, install and connect with a test account.
2. Ask the Agent to list the repository's open issues; verify the actual result.
3. Approve one test issue creation, then independently read the resulting issue.
4. Restart Grain and repeat a harmless read; verify account recovery.
5. Cancel sign-in/revoke access and check useful recovery instructions; remove
   the extension and confirm its tools/account ownership disappear from Grain.

Do not automatically replay a write with an unknown outcome. Organisation policy,
account permissions and the provider's current tool availability can limit access.
These checks are provider acceptance, not a new test framework.

## License

The extension definition and documentation are MIT licensed. GitHub artwork is
excluded from that license and remains subject to GitHub's brand terms. This is
a Grain integration, not a GitHub-authored or GitHub-endorsed extension.
