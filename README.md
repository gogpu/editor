<p align="center">
  <img src="https://raw.githubusercontent.com/gogpu/gogpu/main/assets/logo.png" alt="GoGPU Logo" width="120" />
</p>

<h1 align="center">gogpu/editor</h1>

<p align="center">
  <strong>Pure Go Text/Code Editor Widget</strong><br>
  GPU-accelerated, embeddable, zero CGO.
</p>

<p align="center">
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License"></a>
  <a href="https://github.com/gogpu/editor"><img src="https://img.shields.io/badge/Go-1.25+-00ADD8?logo=go" alt="Go Version"></a>
</p>

---

## Overview

**gogpu/editor** is a reusable native text and code editor widget for Go — like [Monaco Editor](https://github.com/microsoft/monaco-editor) but for Go desktop and WASM applications. GPU-accelerated rendering via [gogpu/gg](https://github.com/gogpu/gg), widget system via [gogpu/ui](https://github.com/gogpu/ui).

### Key Goals

- **Embeddable** — drop into any Go application as a widget
- **GPU-accelerated** — glyph atlas, ClearType LCD, MSDF fallback
- **Pure Go** — zero CGO, cross-compiles everywhere (Windows, macOS, Linux, WASM)
- **Code editor** — syntax highlighting, line numbers, code folding
- **Rich text** — multi-font, styled runs, WYSIWYG editing
- **IDE-ready** — LSP client, DAP client, minimap, diagnostics

### Status

🚧 **Early development.** Architecture defined in ADR-028 (internal).

## Architecture

```
gogpu/editor/
├── document/     # PieceTable document model, undo/redo
├── layout/       # Text layout engine, line breaking, styled runs
├── view/         # Editor widget, gutter, cursor, selection, minimap
├── input/        # Keyboard, mouse, IME
├── syntax/       # Syntax highlighting (TextMate, Tree-sitter)
└── lsp/          # Language Server Protocol client (future)
```

### Enterprise References

| Editor | Key Pattern | What We Take |
|--------|-------------|--------------|
| **VS Code** | PieceTree document model | Efficient insert/delete data structure |
| **Monaco** | MVVM, decorations | Separation of model, view, decorations |
| **Scintilla** | Simple Model-View | 25 years proven, portable |
| **Zed** | GPU-accelerated, GPUI | GPU text rendering patterns |
| **CodeMirror 6** | Immutable state, plugins | Functional state management |
| **Xi-editor** | Rope, async frontend-backend | Data structure research |
| **cosmic-text** | Pure Rust text layout | Pure language text layout patterns |

## Ecosystem

Part of the [gogpu](https://github.com/gogpu) Pure Go GPU ecosystem:

| Repo | Purpose |
|------|---------|
| [gogpu](https://github.com/gogpu/gogpu) | App framework, windowing |
| [wgpu](https://github.com/gogpu/wgpu) | Pure Go WebGPU |
| [gg](https://github.com/gogpu/gg) | 2D graphics, GPU text rendering |
| [ui](https://github.com/gogpu/ui) | GUI toolkit |
| **editor** | **Text/Code editor widget** ← you are here |

## Contributing

Contributions welcome! Architecture decisions and open questions are tracked internally. Join the [discussion](https://github.com/gogpu/gogpu/discussions) to participate.

## License

MIT
