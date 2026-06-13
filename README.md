# Tidepool

A calm, cool dark theme for VS Code — greens, teals, and blues drawn from a single 18-color palette. Designed with red-green color blindness in mind: meaning is carried by brightness and the blue–yellow axis, never by red-versus-green.

The editor and the integrated terminal share the exact same palette, so both surfaces read as one thing.

## Syntax at a glance

A deliberately restrained mapping — a blue family for structure, a green family for data:

- Keywords — teal
- Functions — soft blue
- Types — bright cyan
- Strings & numbers — green
- Properties — green
- Variables — bright green
- Comments — grey

Warm tones stay out of your code. Red and amber are reserved for errors and warnings; green, amber, and red appear only in git decorations and diffs.

## Palette

| Role | Hex |
|------|-----|
| Background | `#333333` |
| Foreground | `#E5E5E5` |
| Keywords (cyan) | `#4FB0C2` |
| Functions (br-blue) | `#AAC8E4` |
| Types (br-cyan) | `#6FC9DA` |
| Strings · numbers · properties (green) | `#42B883` |
| Variables (br-green) | `#5BD39B` |
| Comments (br-black) | `#5C5C5C` |
| Errors (red) | `#C2554D` |
| Warnings (yellow) | `#D6A95C` |
| Git added | `#5BD39B` |
| Git modified | `#E6C275` |
| Git removed | `#D5685C` |
| Cursor / accent | `#4FB0C2` |
| Selection | `#3D5A60` |

The full 16-color ANSI set powers the integrated terminal.

## Try it locally

Two options.

Quick — copy into your extensions folder, then reload:

```sh
cp -r tidepool ~/.vscode/extensions/tidepool-0.1.0
# reload VS Code, then: Preferences > Color Theme > Tidepool
```

Or package and install a VSIX:

```sh
npm install -g @vscode/vsce
cd tidepool
vsce package
code --install-extension tidepool-0.1.0.vsix
```

## Publish to the Marketplace

1. Create a publisher at https://marketplace.visualstudio.com/manage and an Azure DevOps Personal Access Token (with the Marketplace > Manage scope).
2. Set the `publisher` field in `package.json` to your publisher ID (currently `s3mi0tics`).
3. From the project root:

```sh
vsce login <your-publisher-id>
vsce publish
```

### Cursor / Open VSX

Cursor and other VS Code forks install from Open VSX, not the Microsoft Marketplace. To reach them — and your own Cursor — publish there too:

```sh
npm install -g ovsx
ovsx publish tidepool-0.1.0.vsix -p <your-openvsx-token>
```

## Before you publish

- Add a screenshot or two to this README — themes live or die on their gallery preview.
- `icon.png` is a simple placeholder mark; swap it if you'd like something else.

## License

MIT © 2026 Colby Kauk
