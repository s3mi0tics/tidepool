# Development

Maintainer notes for building and publishing Tidepool. Not shipped with the extension.

## Install from source

```sh
npm install -g @vscode/vsce
cd tidepool
vsce package
code --install-extension tidepool-<version>.vsix
```

## Publishing

Tidepool ships to two registries: the **VS Code Marketplace** (for VS Code) and **Open VSX** (for Cursor, VSCodium, Windsurf, and other forks).

A listing only refreshes when a new version is published, so bump `version` in `package.json` first, then rebuild — and publish the same `.vsix` to both registries:

```sh
vsce package
```

### VS Code Marketplace

One-time setup:

- An Azure DevOps organization with an active Azure subscription linked. The free pay-as-you-go tier is fine (publishing never leaves the free tier), but a credit card is required to create the subscription — new orgs can no longer be created without one.
- A Personal Access Token scoped to **Marketplace > Manage**, with Organization set to **All accessible organizations**. A token scoped to a single org causes a 401 at publish time.
- A publisher created at <https://marketplace.visualstudio.com/manage> with ID `s3mi0tics`. The publisher ID is permanent and must match `publisher` in `package.json`. (The Azure DevOps org name is unrelated and need not match.)

```sh
vsce login s3mi0tics            # paste the PAT; vsce caches it in the macOS keychain
vsce publish --packagePath tidepool-<version>.vsix
```

The display name (`displayName` in `package.json`) must be globally unique across all Marketplace extensions, not just themes — hence "Tidepool Color Theme" rather than "Tidepool".

### Open VSX

One-time setup:

- An <https://open-vsx.org> account (log in with GitHub).
- The Eclipse Foundation Open VSX Publisher Agreement signed, under your Open VSX **Profile** tab. Signing requires an Eclipse Foundation account with your **GitHub username** filled into its profile — otherwise the signature is rejected.
- An access token from **Settings → Access Tokens** (only generates once the agreement is signed).

```sh
ovsx create-namespace s3mi0tics -p '<token>'   # first time only
ovsx publish tidepool-<version>.vsix -p '<token>'
```

Or `export OVSX_PAT='<token>'` once and drop the `-p` flag.

## Links

- Marketplace: <https://marketplace.visualstudio.com/items?itemName=s3mi0tics.tidepool>
- Open VSX: <https://open-vsx.org/extension/s3mi0tics/tidepool>
