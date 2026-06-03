# svelte-notoriousbutton

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
![GitHub all releases](https://img.shields.io/github/downloads/rgglez/svelte-notoriousbutton/total)
![GitHub issues](https://img.shields.io/github/issues/rgglez/svelte-notoriousbutton)
![GitHub commit activity](https://img.shields.io/github/commit-activity/y/rgglez/svelte-notoriousbutton)
[![GitHub release](https://img.shields.io/github/release/rgglez/svelte-notoriousbutton.svg)](https://github.com/rgglez/svelte-notoriousbutton/releases/)
![GitHub stars](https://img.shields.io/github/stars/rgglez/svelte-notoriousbutton?style=social)
![GitHub forks](https://img.shields.io/github/forks/rgglez/svelte-notoriousbutton?style=social)

**svelte-notoriousbutton** is a Svelte button component with CSS-only visual
effects.

## Installation

```bash
npm install @rgglez/svelte-notoriousbutton
```

## Usage

### Svelte 3 / 4

```svelte
<script>
  import NotoriousButton from '@rgglez/svelte-notoriousbutton/svelte4';
</script>

<NotoriousButton label="Click me" effect="sweep" />
```

### Svelte 5

Bare import (default export points to Svelte 5):

```svelte
<script>
  import NotoriousButton from '@rgglez/svelte-notoriousbutton';
</script>

<NotoriousButton label="Click me" effect="glow" />
```

Or explicit subpath:

```svelte
<script>
  import NotoriousButton from '@rgglez/svelte-notoriousbutton/svelte5';
</script>

<NotoriousButton label="Click me" effect="glow" />
```

## Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `label` | `string` | `'Click me'` | Button text |
| `effect` | `'sweep' \| 'glow' \| 'shake' \| 'pulse' \| 'border-sweep' \| ''` | `''` | Visual effect |
| `trigger` | `'hover' \| 'auto'` | `'hover'` | Fire effect on hover or continuously |
| `class` | `string` | `''` | Additional CSS classes |
| `style` | `string` | `''` | Inline styles |

## Effects

| Value | Description |
|-------|-------------|
| `sweep` | Glossy diagonal shine that slides across on hover |
| `glow` | Radial ring and brightness highlight on hover |
| `shake` | Vibration animation triggered on hover |
| `pulse` | Continuous breathing scale animation; pauses on hover |
| `border-sweep` | Conic-gradient light sweeps around the button border |

All effects are implemented in pure CSS — no JavaScript at runtime.

## Examples

```svelte
<!-- Default -->
<NotoriousButton label="Save" />

<!-- Sweep shine -->
<NotoriousButton label="Submit" effect="sweep" />

<!-- Glow ring -->
<NotoriousButton label="Confirm" effect="glow" />

<!-- Shake on hover -->
<NotoriousButton label="Delete" effect="shake" style="background: #dc2626;" />

<!-- Continuous pulse -->
<NotoriousButton label="New" effect="pulse" />

<!-- Custom class and style -->
<NotoriousButton label="Custom" effect="sweep" class="my-class" style="border-radius: 999px;" />
```

## CSS customization

Import the shared stylesheet directly to override variables:

```js
import '@rgglez/svelte-notoriousbutton/notorious-button.css';
```

The `.notorious-btn` class is applied to every button. Effect classes follow the
pattern `.effect-{name}`.

## Development

### Prerequisites

- Node.js
- npm
- git

### Makefile targets

| Target | Description |
|--------|-------------|
| `make tags` | List all git tags sorted by version |
| `make patch` | Bump the patch version, commit, tag, and push to origin |
| `make publish` | Publish the current version to npm |
| `make release` | Run `patch` then `publish` in one step |

Typical release flow:

```bash
# Review changes, then:
make release
```

This will:

1. Increment the patch version in `package.json` (e.g. `1.0.0` → `1.0.1`)
2. Commit `package.json` with message `chore: bump version to X.Y.Z`
3. Create git tag `vX.Y.Z`
4. Push branch and tag to origin
5. Run `npm publish --access public`

To publish without bumping the version:

```bash
make publish
```

To inspect existing tags:

```bash
make tags
```

## Example

You can try the example (Svelte 5) in the `example` directory. You can also view a [live example](https://svelte.dev/playground/04642e5a0de64dc7a4785e928ec12f18?version=5.56.1).

## License

Copyright 2026 Rodolfo González González.

Licensed under [Apache v2.0](https://www.apache.org/licenses/LICENSE-2.0)
license. Please read the [LICENSE](LICENSE) file.