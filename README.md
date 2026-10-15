# GitHub for Grain

Artwork candidate **0.1.2** separates the 512×512 listing icon from three wide
gallery images. URL, OAuth identity and toolset options are unchanged. Source
validation and packaging are local checks; the exact candidate still needs
registry review, signing and public activation. Existing published evidence below
continues to refer to 0.1.1. See [artwork sources](assets/README.md).

A Grain-authored MCP extension connecting the Agent to
[GitHub's official remote MCP server](https://github.com/github/github-mcp-server).
GitHub operates the server at `https://api.githubcopilot.com/mcp/`; this repository
contains only the Grain extension definition and store listing. There is no native
worker, JavaScript bundle, local MCP process or custom GitHub API implementation.

## Status

Version **0.1.1** is the package-owned transport-options candidate. It declares
`x-mcp-toolsets: all` in `transport.headers`; Grain's shared SDK transport
forwards the option without a GitHub-specific runtime branch. The base URL is
unchanged, preserving the existing first-party OAuth resource/client binding.
The declaration changes the advertised catalogue, not account permissions or
approval requirements. The provider remains responsible for its tools.

The tester update is published at catalogue index 4, source tag `v0.1.1`
(`394176037b46ecbfde34d7af0996a505b3352400`). Public delivery, matching signed
update/account retention, 100-tool discovery, private read/restart and representative
issue create/update/close and branch/file writes pass. The configured Gemini route
needed an external 9router schema fix; two fixture errors were corrected. This
does not certify all tools/account permissions. See [verification](VERIFICATION.md).

Supported tester alphas use Grain's registered GitHub App and connection-owned
vault; users sign in rather than create their own developer application.
Community public-client OAuth onboarding is supported by the current shared
contract; it is not a secret stored in this descriptor. No OAuth identity or repository grant
is changed by this candidate.

## Package and submit

Use the maintained CLI from the Grain checkout; no npm install/build is needed:

```powershell
cargo build --locked -p grain-ext-cli --bin grain-ext
# Run the resulting grain-ext executable from this repository:
grain-ext doctor
grain-ext pack
```

The artifact is `com.grain.github-0.1.1.mcp.json`. `DESCRIPTION.md` is store copy;
README is maintainer documentation. `media/cover.webp` is the signed store artwork.
The original GitHub integration marks are under `assets/`; see their
[attribution and terms](assets/README.md).

After committing source and tagging the reviewed version, use the actual full
commit SHA rather than an example pin:

```powershell
grain-ext submit --registry C:\path\to\grain-extensions --repo https://github.com/Punit-Dethe/grain-github-extension --tag v0.1.1 --commit <actual-full-commit-sha> --license MIT --contact https://github.com/Punit-Dethe/grain-github-extension/issues
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
