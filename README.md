# Tidepool

A calm, cool dark theme for VS Code — greens, teals, and blues from a single palette, built with red-green color blindness in mind. It ships in two depths, so you can pick the contrast that suits your screen:

- **Tidepool** — a soft mid-gray background (`#333333`)
- **Tidepool Deep** — a darker background (`#2F2F2F`) with more separation between surfaces

Both share the same syntax colors, and the editor and integrated terminal draw from one palette so the two surfaces read as a single environment.

## Syntax at a glance

A deliberately restrained mapping — a blue family for structure, a green family for data:

- Keywords — teal
- Functions — soft blue
- Types — bright cyan
- Strings & numbers — green
- Properties — green
- Variables — bright green
- Comments — gray

Warm tones stay out of your code: red and amber are reserved for errors and warnings, and the git colors live only in the gutter and diffs.

## Accessibility

Tidepool is designed around red-green color blindness. Syntax meaning rests on brightness and the blue–yellow axis rather than a red-versus-green difference, and the core token colors clear WCAG 2.1 AA contrast against the editor background. Errors use a warm orange instead of pure red, so they stay visible to red-weak vision.

## Choosing a variant

Install once, then switch any time: **Cmd/Ctrl+K Cmd/Ctrl+T** → *Tidepool* or *Tidepool Deep*.

## Palette

| Role | Hex |
|------|-----|
| Editor — Tidepool / Deep | `#333333` / `#2F2F2F` |
| Foreground | `#E5E5E5` |
| Keywords (cyan) | `#4FB0C2` |
| Functions (soft blue) | `#AAC8E4` |
| Types (bright cyan) | `#6FC9DA` |
| Strings · numbers · properties (green) | `#42B883` |
| Variables (bright green) | `#5BD39B` |
| Comments | `#6E6E6E` |
| Errors (orange) | `#CC6A4A` |
| Warnings (amber) | `#D6A95C` |
| Git added / modified / removed | `#5BD39B` / `#E6C275` / `#D5685C` |

The full 16-color ANSI set powers the integrated terminal.

## Install from source

```sh
npm install -g @vscode/vsce
cd tidepool
vsce package
code --install-extension tidepool-0.1.0.vsix
```

## Publish

1. Create a publisher at https://marketplace.visualstudio.com/manage with an Azure DevOps Personal Access Token (Marketplace > Manage scope).
2. Set `publisher` in `package.json` to your publisher ID.
3. `vsce login <publisher>`, then `vsce publish`.

For Cursor and other forks, also publish to Open VSX: `npm install -g ovsx`, then `ovsx publish tidepool-0.1.0.vsix -p <token>`.

## License

MIT © 2026 Colby Kauk
